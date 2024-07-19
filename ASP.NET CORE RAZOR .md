
# REQUIREMENTS

1. web server : to host websites, to create domains,processing server side language

- html files are directly compiled by browser(has parser that compiles html and css codes), no new compiler needed.
- browser doesn't have C# compiler
- web server compiles server side language(C# code).
- web server has built in compiler for c#


2. physical path : the path where the file is stored
3. virtual path : any that starts with http

http://localhost/hello.html

4. protocol : using HTTPS protocol(carry data between client and server)

5. Client : browser (chrome,morzilla,edge,firefox,safari)


- IIS (inbuilt web server in windows)
1. write click on default site , click add application.
2. enter the alias name amd path of folder where file is stored
3. click Ok
4. Click Content View (shows what pages are there )




- to develop a web application in .NET we have two ways
1. using framework : using asp.net
2. using core : using asp.net core Razor or asp.net core mvc



## WHY NOT ASP.NET

-  ASP.NET only for windows , whereas asp.net core is for windows,mac and linux

- asp.net core has better performance

- asp.net core runs on both .NET core and framework

- Asp.Net supports web forms (everything is drag and drop Eg: drag and drop button, the code is written automaticaaly in web form)

- Aso.Net uses only IIS web server, whereas Asp.Net core is not dependent on IIS

- Asp.Net core supports more languages than asp.net

- asp.net core stores files in json whereas asp.net stores in xml

- asp.net core supports containers such as docker

- asp.net core -> no need to comiple the file again and again when changes are made in code, refreses automatically once file is saved.



# DIFFERENCE BETWEEN RAZOR PAGES AND MVC PAGES

- both are cross platform(supports windows , linux, mac)

- both supports multiple webservers

- razor is suitable for very small and intermediate project

- mvc designed for very large project

- razor pages lacks few features comapred to mvc

- in razor each page contains its own code (separate .cs file), mvc all the codes is centralized (common .cs file)


![alt text](image-69.png)     



# RAZOR 

- razor is server side pages (web server process the page)

- includes C#,html,css javascript 

- syntax begins with @ (@ repersents c# code)

![alt text](image-70.png)

- file extension is .cshtml 

- lightweight 

- cross platform


- Files that are created when we create a razor project

1. Dependencies : where packages installed are stored

2. Connected Services : stores online services ( Web service or API Service)/ services used from online site(we can use the code we need that already exists online)

3. Properties : has launchsettings.json (has information about web servers (Kestrel webserver))

- by default .Net core uses kestrel web server( runs on all platforms)

- visual studio has two web servers : 
       1. IISExpress web server (only for windows) => basic version of iis
       2. kestrel web server

4. wwwRoot : all client side pages (html,css,javascript,bootsrap,xml,json etc)

5. Pages : for server side pages (C# pages) 
      - Layout pages : contains common features of all pages
      - viewimports : contains common namespaces
      - viewstart : layout page to be used.(to apply the layout page)

6. AppSettings.json : stores configuration settings like database path, logging,etc

7. Program.cs : contains logic to create kestral web server , authentication programs, session features and exception handling features
```c#
var builder = WebApplication.CreateBuilder(args); //to create kester web server
```


- to call methods of diffrent class we use @Model


- to take input from user to calcualte two numbers

```c#
//in cs page
 public class mycls()
 {

     public string txt1 { get; set;}
     public string txt2 { get; set;}

 }


 public class IndexModel : PageModel
{
    public int res { get; set; }


    public void OnPost(mycls obj)
    {
        //this logic will be executed when submit is clicked
         res = int.Parse(obj.txt1) + int.Parse(obj.txt2);

    }
}


//in cshtml

<form method="post">
    <input type="text" name="txt1"/>
    <input type="text" name="txt2"/>
    <input type="submit" value="Addnumbers"/>

</form>

@Model.res
```

```html
<a class="btn btn-primary" asp-page="viewContacts">Viewcontact</a>

```

- Query String -> pass data from one page to another


- OnGet Method -> intialization code is written , what logic hould be displayed when oage is loaded -> called when page is loaded from server to client

- Onpost method : to send data from client to server




- The Program.cs file is the program.cs file in console app , to convert to razor project the code s written in program.cs


```c#
// will also load  launchsettings.json and appsettings.json

//creates and loads kestral server in memory

// will return an object(webapplication builder)

//using this return type , we can configure add a services , dependency injection and middleware
var builder = WebApllication.CreateBuilder(args);

//to convert to razor project 
builder.Services.AddRazorPages();

// to load the services to kestral web server
// using app we can define rules for project
// app is used to use the services
// the order of execution of services 
//Eg: app.UseAuthentication();
    //app.MapRazorPages();
var app = builder.Build();

// if wrong url entered then display error message with status code
app.UseStatusCodePages();

//now if wrong url is entered , it will redirect to error page and the wrong url entered is changed to errorpage url
app.UseStatusCodePagesWithRedirects("ErrorPage");

// it will redirect to errorpage but the wrong url stays the same 
app.UseStatusCodePagesWIthReExecute("/ErrorPage");
```



