## Deploy ASP.Net application to Azure App Service using VSTS

This lab shows how you can deploy an **ASP.Net application to Azure App Service using an CI/CD pipeline in Visual Studio Team Services**.

## Pre-requisites
1. Microsoft Azure Account:</b> You will need a valid and active azure account for the labs.

1.  You need a <b>Visual Studio Team Services Account</b> and <a href="http://bit.ly/2gBL4r4">Personal Access Token</a>
<


## Setting up the project
1. Use <a href="https://vstsdemogenerator.azurewebsites.net" target="_blank">VSTS Demo Data Generator</a> to provision a project on your VSTS account 

 ![](images/1.png)

 2. Select **PartsUnlimited** for the template

 ![](images/2.png)

3. Once the project is provisioned, select the URL to navigate to the project that you provisioned


## Configuring the CI/CD pipeline

1. Let's start from code . Navigate to the **Code** hub 

   <img src="images/4.png">

1. We have an ASP.NET app code provisioned by the demo generator system. We will deploy this to Azure app service

1. We have a Continious Integration (CI) build setup ton run upon a code commit. Let's make a simple change to the code to trigger the CI build

2. Open the file **Index.cshtml** by navigating to the path **PartsUnlimited-aspnet45/src/PartsUnlimitedWebsite/Views/Home/Index.cshtml**

   <img src="images/5.png">

3. Click on edit and change the code as **50%** to **70%** in the line number **28**.

   <img src="images/6.png">

4. **Commit** after doing the changes. 

5. Go to the **Build** tab to see the CI build running in progress.

   <img src="images/7.png">

   <img src="images/8.png">

6. Once the build is completed, you can see the summary which shows **test results, code coverage** etc as shown below.

   <img src="images/9.png">

## Continuous Deployment

We are using **Infrastructure as a Code** in our release pipeline which provides the required infrastructure on Azure Environment during the deployment phase. 

Once the release is successful, you can login to [Azure Portal](https://portal.azure.com) and search a **Resource Group** with the name **AspDotNet** that would have got created. It would be associated with few other resources like **SQL server, SQL DB, WebApps** etc as shown below.

<img src="images/10.png">

Navigate to one of the WebApp from the resource group and you should see the application is deployed successfully with the changes made earlier as shown.

<img src="images/11.png">
