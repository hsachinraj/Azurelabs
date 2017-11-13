## Managing Technical Debt with Visual Studio Team Services and SonarQube 

In this lab, you will be introduced to Technical debt, how to configure your Team Build Definitions to use SonarQube, how to understand the analysis results and finally how to configure quality profile to control the rule set used by SonarQube for analyzing your project.

## Pre-requisites

1. **Microsoft Azure Account:** You will need a valid and active azure account for the labs

2. You need a **Visual Studio Team Services Account** and <a href="http://bit.ly/2gBL4r4">Personal Access Token</a>

3. You will need a **SonarQube** server

## Setting up the project

1. Use <a href="https://vstsdemogenerator.azurewebsites.net" target="_blank">VSTS Demo Data Generator</a> to provision a project on your VSTS account.

   ![](images/1.png)

2. Select **SonarQube** for the template.

3. Once the project is provisioned, select the URL to navigate to the project that you provisioned.

## Setting up SonarQube Server on Azure

1. Click on **Deploy To Azure** to spin up a SonarQube Server on Azure VM.

   <a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fhsachinraj%2FAzurelabs%2Fmaster%2Fsonarqube%2Ftemplates%2Fazuredeploy.json"><img src="http://azuredeploy.net/deploybutton.png"></a>

   Provide the following valid parameters as shown in the table.

   <table width="100%">
   <thead>
      <tr>
         <th width="50%"><b>Parameter Name</b></th>
         <th><b>Description</b></th>
         <th><b>Default Value</b></th>
      </tr>
   </thead>
   <tr>
      <td>sqVM_AppName</td>
      <td>Name of the VM that SonarQube will be installed upon</td>
      <td>None</td>
   </tr>
   <tr>
      <td>sq_PublicIP_DnsPrefix</td>
      <td>The prefix of the public URL for the VM on the Internet (Max 63 chars, lower-case). It should match with the following regular expression: ^[a-z][a-z0-9-]{1,61}[a-z0-9]$ or it will raise an error. This will be used to build the fully qualified URL for the SonarQube site in the form of http://[sq_PublicIP_DnsPrefix].[AzureRegion].cloudapp.azure.com Ex: A value of "my-sonarqube" will result in a URL of http://my-sonarqube.eastus.cloudapp.azure.com if the ARM template is deployed into a storage account hosted in the EASTUS Azure region</td>
      <td>None</td>
   </tr>
   <tr>
      <td>sqVM_AppAdmin_UserName</td>
      <td>Local Admin account name for the SonarQube VM</td>
      <td>None</td>
   </tr>
   <tr>
      <td>sqVM_AppAdmin_Password</td>
      <td>Password for the SonarQube VM Local Admin account</td>
      <td>None</td>
   </tr>
   <tr>
      <td>sqDB_Admin_UserName</td>
      <td>Admin account name for Azure SQL Server</td>
      <td>None</td>
   </tr>
   <tr>
      <td>sqDB_Admin_Password</td>
      <td>Password for Azure SQL Server Admin account</td>
      <td>None</td>
   </tr>
   <tr>
      <td>sqDB_DBName</td>
      <td>Name of the SonarQube DB on the Azure SQL Server</td>
      <td>sonarsql</td>
   </tr>
   <tr>
      <td>sqDB_DBEdition</td>
      <td>Edition of Azure SQL Server to create, Allowed Values: Basic, Business, Premium, Standard, Web</td>
      <td>Basic</td>
   </tr>
   <tr>
      <td>sqStorage_AcctType</td>
      <td>Type of Azure Storage Acct to create, Standard_LRS, Standard_ZRS, Standard_GRS, Standard_RAGRS, Premium_LRS</td>
      <td>Basic</td>
   </tr>
   </table>

2. Once the deployment is successful, you should see all the resources in the resource group in Azure Portal.

   <img src="images/2.png">

3. Access the **SonarQube** portal by providing its public address in the browser. The address format is **http://[sq_PublicIP_DnsPrefix].[AzureRegion].cloudapp.azure.com:9000**.

   >You can login to the SonarQube Portal using the following credentials- **Username= admin, Password= admin**

   <img src="images/3.png">


## Configure SonarQube Server

1. Login to the portal with the above mentioned credentials.

2. Click on **Administration** and go to **Projects-->Management**

   <img src="images/7.png">

3. Create Project as shown with the following details.

   <img src="images/8.png">


## Configuring CI pipeline for SonarQube

1. We have a **Java** Application provisioned by the demo generator system. We will run the analysis for the same.

2. Open the build definition **SonarQube.CI** to explore the tasks. Below is the table which gives you the glimpse of the tasks that is being used in the current build definition.

   <table width="100%">
   <thead>
      <tr>
         <th width="50%"><b>Tasks</b></th>
         <th><b>Usage</b></th>
      </tr>
   </thead>
   <tr>
      <td><a href="http://bit.ly/2lvftfo"><b>Maven</b></a> <img src="images/maven.png"></td>
      <td>Used to build Java code</td>
   </tr>
   <tr>
      <td><a href="http://bit.ly/2rU8y12"><b>SonarQube Scanner CLI</b></a> <img src="images/sonarqube.png"> </td>
      <td>Performs SonarQube analysis of the source code</td>
   </tr>
   <tr>
      <td><a href="http://bit.ly/2grMxTQ"><b>Copy Files</b></a> <img src="images/copy-files.png"> </td>
      <td>Used to Copy files from source to destination folder using match patterns </td>
   </tr>
   <tr>
      <td><a href="http://bit.ly/2yBgXde"><b>Publish Build Artifacts</b></a> <img src="images/publish-build-artifacts.png"> </td>
      <td> Used to share the build artifacts </td>
   </tr>
   </table>

3. Configure the **SonarQube Scanner CLI** task with the **Project Settings** that you just created above as shown.

   <img src="images/9.png">

3. Save and trigger the build to see the in progress status.

   <img src="images/5.png">

4. Once the build is completed, you can see the summary which shows **test results, code coverage results** as shown below.

   <img src="images/6.png">

5. Navigate to **SonarQube** Portal to see the analysis results by selecting the project.

   <img src="images/10.png">

   <img src="images/11.png">



   

