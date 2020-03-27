# Live Project
## Introduction
For two weeks of my course at The Tech Academy I was assigned to a live project assignment where I worked with my peers to create a MVC web application in C#. The site that we created was for a client in Portland, Oregon. I personally was able to create a format to display their sponsors in a partial viewe at the bottom of the main page. Working on the live projects really helped me to grow as a developer. I was able to work in a team to bring a project to life and showcase and grow our skills in the process.
## CSS
```
/*Sponsors Partial View*/

.sponsors-partial-column {
    width: 10%;
    display: inline-block;
    margin: 50px;
    vertical-align: middle;
}
```
## Code to display in Index.cshtml 
This code is what makes it all display on the page.
```
@*Sponsor section*@
@*<div>
        @Html.Partial("_SponsorsPartial")
    </div>*@
@{Html.RenderAction("List", "Sponsors");}
```
## Main code
This code inserts the sponsor photos into the display.
```
@model IEnumerable<TheatreCMS.Models.Sponsor>
<div class="text-center">
    <h3 class="sponsor-title">Our Sponsors</h3>

    @foreach (var item in Model)
    {
        <figure class="sponsors-partial-column">
            <img class="sponsor-partial-pic" src="data:image;base64,@System.Convert.ToBase64String(item.Logo)" />
            <br />
            <figcaption class="sponsor-text">@Html.DisplayFor(modelItem => item.Name)</figcaption>
        </figure>
    }
    <div class="center">
        <button type="button" class="btn btn-lg sponsor-donate-btn">Donate</button>
    </div>

</div>
```
