# Introduction 
Project for an Onboarding Challenge on the Azure DevOps EEE team.

# Challenge
Build a web app and deploy it to Azure in the 2 following ways:

1. Classic Pipelines
    - Build Pipeline
    - Release Pipeline
2. YAML Pipeline
3. Use Elastic Pool / VMSS

# Choices made
- Started with the default build pipeline template for ASP.NET Core web apps.
    - Chose windows-2022 MS-hosted agents to be reasonably up to date, but avoid unexpected issues when windows-latest changes to a more recent version.
    - Disabled the "Test" task, as there are currently no tests.


# Future Ideas
- Use ARM or bicep template to deploy Azure resources
- Approvals for deployments - specifically explore alternatives for YAML
- Merge Classic build & release pipelines
- More stages for deployment - a Test and Prod env with gates. (for example using App Service Slots & Swaps)
- Check changes between AzureRmWebAppDeployment and AzureWebApp tasks ("AzureRM" seems to indicate that it's older)
- set up & use self-hosted agents
- Web App specific: explore the various ways to set variables (web.config, Web App settings)
- How to replicate pipeline to various deployments (i.e. how to ensure Test is same as prod)

# Minor "bugs" found
- "Save & Run" while using a duplicate pipeline name results in an error stating that the name is already in use (expected), but then the UI gets stuck at "starting run..." (not expected). Might be handled more gracefully - as not to require a page reload.