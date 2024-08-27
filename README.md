# Simple Streamlit AZD Template

The most basic streamlit "hello world" application as an AZD template ready for Azure App Service

![system diagram](diagram.png)

## Usage

1. Install AZD and run the following command to initialize the project.

```bash
azd init --template MiguelElGallo/simple-streamlit-azd
```

This command will clone the code to your current folder and prompt you for the following information:

- `Environment Name`: This will be used as a prefix for the resource group that will be created to hold all Azure resources. This name should be unique within your Azure subscription.

2. Run the following command to build a deployable copy of your application, provision the template's infrastructure to Azure and also deploy the application code to those newly provisioned resources.

```bash
azd up
```

This command will prompt you for the following information:
- `Azure Location`: The Azure location where your resources will be deployed.
- `Azure Subscription`: The Azure Subscription where your resources will be deployed.

> NOTE: This may take a while to complete as it executes three commands: `azd package` (builds a deployable copy of your application), `azd provision` (provisions Azure resources), and `azd deploy` (deploys application code). You will see a progress indicator as it packages, provisions and deploys your application.

3. Then make changes to stlitapp.py and run `azd deploy` again to update your changes.

## Notes

This uses the F1 (free) SKU for app service, which has limited CPU and RAM resources.

See the [pricing calculator](https://azure.microsoft.com/en-au/pricing/calculator/) for details on paid SKUs replace the SKU option with a suitable choice.

Based on the this [great template:](https://github.com/tonybaloney/simple-flask-azd)

Added support for `azd pipeline config`, enabling creation of CI/CD pipeline for GitHub Actions. Note this is still a [beta](https://learn.microsoft.com/en-us/azure/developer/azure-developer-cli/configure-devops-pipeline?tabs=GitHub) feature in AZD. 