---
description: This template sets up Azure AI Studio Hub with public access disabled and depdendent resources. It also creates a VM behind a VNET and enables the hub to utlized it as a compute resources in a private network.
page_type: sample
products:
- azure
- azure-resource-manager
urlFragment: aistudio-vm-private
languages:
- bicep
- json
---
# Azure AI Studio Private Endpoints Setup

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fctava-msft%2Faistudio-vm%2Fmain%2Fmain.json)

Azure AI Studio is built on Azure Machine Learning as the primary resource provider and takes a dependency on the Cognitive Services (Azure AI Services) resource provider to surface model-as-a-service endpoints for Azure Speech, Azure Content Safety, and Azure OpenAI service. An 'Azure AI hub' is a special kind of 'Azure Machine Learning workspace', that is kind = "hub".

A VM is added as a connected compute resource for secure use of Azure OpenAI Service.

## Resources

The following table describes the resources created in the deployment:

| Provider and type | Description |
| - | - |
| `Microsoft.Compute` | `An Azure VM Compute` |
| `Microsoft.CognitiveServices` | `An Azure AI Services as the model-as-a-service endpoint provider` |
| `Microsoft.MachineLearningServices` | `An Azure AI Hub` |

## Commands to generate files from main.bicep:

Generate ARM Template from bicep file:

```
az bicep build --file main.bicep
```

main.parameters.json was copied over from another project.
if needed, edit vmSize values in main.json for your region.

## Learn more

If you are new to Azure AI studio, see:

- [Azure AI studio](https://aka.ms/aistudio/docs)

If you are new to Azure virtual machines, see:

- [Azure Virtual Machines](https://azure.microsoft.com/services/virtual-machines/).
- [Azure Virtual Machines documentation](https://learn.microsoft.com/azure/virtual-machines/)

If you are new to template deployment, see:

- [Azure Resource Manager documentation](https://learn.microsoft.com/azure/azure-resource-manager/)
- [Quickstart: Create an Ubuntu Linux virtual machine using an ARM template](https://learn.microsoft.com/azure/virtual-machines/linux/quick-create-template)