## Deploy Asp.Net application to Azure App Service using VSTS


This lab will show you how you can deploy an ASP.Net application to Azure App Service using an CI/CD pipeline in Visual Studio Team Services.

## Pre-requisites
<table>
   <tr>
      <td valign="top">
         <img src="images/azure.png" />
      </td>
      <td><b>Microsoft Azure Account:</b> You will need a valid and active azure account for the labs.</td>
   </tr>
   <tr>
      <td valign="top">
         <br>
         <img src="images/vstsdemogen.png"/>
      </td>
      <td> You need a <b>VSTS account name</b> and <b>PAT</b>. Refer <a href="http://bit.ly/2gBL4r4">here</a> for more information on PAT. </td>
   </tr>
</table>

Use <a href="https://vstsdemogenerator.azurewebsites.net">VSTSDemoDataGenerator</a> to provision <b>PartsUnlimited</b> project.
## Configuring the CI/CD pipeline

1. Navigate to the project that was created and go to **Code** hub.

   <img src="images/4.png">

2. Open the file <b>Index.cshtml</b> by navigating to the path <b>PartsUnlimited-aspnet45/src/PartsUnlimitedWebsite/Views/Home/Index.cshtml</b>

   <img src="images/5.png">

3. Click on edit and change the <b>line number 28</b> to <b>70%</b>.

   <img src="images/6.png">
