# Host a web application with Azure App Service

Learning objectives
- Use the Azure portal to create an Azure App Service web app.  
- Use developer tools to create the code for a starter web application.  
- **Deploy your code to Azure App Service**.  

## Review

What is AZ App Service
> Azure App Service is a fully managed web application hosting platform.  
> This platform as a service (PaaS) offered by Azure **allows you to focus on designing and building your app while Azure takes care of the infrastructure to run and scale your applications.**

Usage of Deployment Slots
> you can create a staging deployment slot where you can push your code to test on Azure.   
> If test is ok. you can easily swap the staging deployment slot with the production slot.   

Usage of Continuous integration/deployment support in AZ Portal  
Connect your web app with Azure DevOps, GitHub, Bitbucket, FTP, or a local Git repository on your development machine, and App Service will do the rest for you by automatically syncing your code and any future changes on the code into the web app.

With Azure DevOps, you can define your own build and release process that compiles your source code, runs the tests, builds a release, and finally deploys the release into your web app every time you commit the code. 

Integrated Visual Studio publishing and FTP publishing
In addition to being able to set up continuous integration/deployment for your web app, you can always benefit from the tight integration with Visual Studio to publish your web app to Azure via Web Deploy technology.   
App Service also supports FTP-based publishing for more traditional workflows.  

