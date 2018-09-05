    @using System.Globalization
    @using System.Threading

    @{
        var user = @User.Identity.Name.Split('\\')[1].Replace('.', ' ');
        CultureInfo cultureInfo = Thread.CurrentThread.CurrentCulture;
        TextInfo textInfo = cultureInfo.TextInfo;
        var userNameCapital = textInfo.ToTitleCase(user);
    }

    <nav class="navbar navbar-expand-lg navbar-dark bg-primary fixed-top">
        <div class="container">
            @Html.ActionLink("Scalehouse", "Index", "Home", new { area = "" }, new { @class = "navbar-brand" })
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarColor02" aria-controls="navbarColor02" aria-expanded="false" aria-label="Toggle navigation" style="">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarColor02">
                <ul class="navbar-nav ml-auto">
                    <li class="text-white">
                        Hello, @userNameCapital
                    </li>
                </ul>
            </div>
        </div>
    </nav>
