## Deploy Asp.Net application to Azure App Service using VSTS


In this lab we are going to discuss about **Deploying Asp.Net application to Azure App service using Visual Studio Team Services**.

**Pre-requisites**

- **Visual Studio Team Services Account**: If you don't have, you can sign up from [here](https://www.visualstudio.com/))
- **Microsoft Azure Account**: You will need a valid and active azure account for the labs. If you do not have one, you can sign up for a [free trial](https://azure.microsoft.com/en-us/free/)

   - If you are a Visual Studio Active Subscriber, you are entitled for a $50-$150 credit per month. You can refer to this [link](https://azure.microsoft.com/en-us/pricing/member-offers/msdn-benefits-details/) to find out more including how to activate and start using your monthly Azure credit.

   - If you are not a Visual Studio Subscriber, you can sign up for the FREE [Visual Studio Dev Essentials](https://www.visualstudio.com/dev-essentials/) program and get $25 per month of Azure credits.

- Use the [Visual Studio Team Services Demo Data generator](https://vstsdemogenerator.azurewebsites.net/) to provision a project with pre-defined data on to your Visual Studio Team Services account. Please use the **PartsUnlimited** template to follow the hands-on-labs.

1. From your browser, go to [VSTSDemoGenerator](https://vstsdemogenerator.azurewebsites.net)

2. Provide VSTS **account name** and **PAT.** Click on **Verify & Continue**

   <img src="images/1.png" >

3. Provide a name for the team project **AspDotNet** and select **PartsUnlimited** template from the list.

   <img src="images/2.png" >

4. Click on **Create Project**. You should see project creation status below.

   <img src="images/3.png">

5. Navigate to the project that was created and go to **Code** hub.

   <img src="images/4.png">
