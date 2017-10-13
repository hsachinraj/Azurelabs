## Working with Jenkins

This lab shows how you can integrate Team Servcies and Jenkins. You can store your code in VSTS and continue to use Jenkins for your continuous integration builds. We will see how you trigger a Jenkins build when you push code to your team project's Git repository or when you check code in to Team Foundation version control

## Pre-requisites
1. Microsoft Azure Account:</b> You will need a valid and active azure account for the labs.

1.  You need a <b>Visual Studio Team Services Account</b> and <a href="http://bit.ly/2gBL4r4">Personal Access Token</a>


## Setting up the project
1. Lets set up a Jenkins VM on Azure

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fhsachinraj%2FAzurelabs%2Fmaster%2Fjenkins%2Ftemplate%2FjenkinsVM.json">
<img src="http://azuredeploy.net/deploybutton.png"/>
</a>

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fhsachinraj%2FAzurelabs%2Fmaster%2Fjenkins%2template/jenkinsVM.json">
<img src="http://armviz.io/visualizebutton.png"/>
</a>

1. Use <a href="https://vstsdemogenerator.azurewebsites.net" target="_blank">VSTS Demo Data Generator</a> to provision a project on your VSTS account 



 2. Select **PartsUnlimited** for the template



3. Once the project is provisioned, select the URL to navigate to the project that you provisioned
