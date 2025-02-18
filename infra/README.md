# Installation

The environment can provisioned using the Bicep templates inclulded with the project and executed in a number of ways including:

      1. Azure CLI
      2. GitHub Actions
      3. Azure DevOps
      4. Azure Portal

We will provide examples of the first two methods in this document. Manual provisioning using the Azure CLI or continuous delivery via GitHub Actions.

<br/>

## Deploying the Bicep templates using the Azure CLI

#### :wrench: CREATING THE RESOURCE GROUP ####

Before executing any of the following Bicep templates, you first need to login to your Azure account using the Azure CLI `az` command line tool:

```bash
az login
```

Then, create a resource group if it does not already exist:

```bash
az group create --name <ResourceGroupName> --location <Location>
```

Replace `<ResourceGroupName>` and `<Location>` with your preferred resource group name and Azure location, respectively.

<br/>

#### :wrench: PROVISIONING THE AI DEPENDENCIES

To deploy the required AI services, deploy the `ai.bicep` file with the `az deployment group create` command:

```bash
az deployment group create --resource-group <ResourceGroupName> --template-file ai.bicep
```

Replace `<ResourceGroupName>` with the name of the resource group you created.

This command will deploy all the resources defined in the `ai.bicep` file to the specified resource group. The `ai.bicep` file should be located in the same directory from which you're running the command. If it's in a different location, you would need to specify the full path to the file in the `--template-file` argument.

Please ensure that you have the Azure CLI installed and you're logged in to your Azure account before running these commands.

<br/>

#### :wrench: PROVISONING THE WEB INFRASTRUCTURE

To deploy the required web infrastructure, deploy the `web.bicep` file with the `az deployment group create` command:

```bash
az deployment group create --resource-group <ResourceGroupName> --template-file web.bicep
```

Replace `<ResourceGroupName>` with the name of the resource group you created.

This command will deploy all the resources defined in the `web.bicep` file to the specified resource group. The `web.bicep` file should be located in the same directory from which you're running the command. If it's in a different location, you would need to specify the full path to the file in the `--template-file` argument.

Please ensure that you have the Azure CLI installed and you're logged in to your Azure account before running these commands.

<br/>

## Deploying infastructure continuously using GitHub Actions

Coming soon...    
