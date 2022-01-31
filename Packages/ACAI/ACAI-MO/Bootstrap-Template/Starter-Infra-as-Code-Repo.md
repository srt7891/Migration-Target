
The starter IaC code Repository part of this project contains the ARM templates and Terraform manifests to create foundational resources like Vnets, subnets, VMs etc in Azure. Reference code repositories along with the reference CI/CD Pipelines will help saving time to the project team.


| <span style="color:blue">For an extensive library of IaC code blocks to provision Azure resources in various patterns and combinations, refer the **[Bootstrap guidance](https://dev.azure.com/GoldenCopy/ACAI-Modernization-Bootstrap-Golden-Copy/_wiki/wikis/Project-Wiki/183/Bootstrap-Template?anchor=complete-set-of-iac-code-modules-%26-pipelines)** on how to leverage ACAI Domain's well maintained [IaCS repository](https://aka.ms/IaCS)</span> |
|--|


#Prerequisites
Before executing the starter pipelines there are some prerequisites to be configured. 

1. **KEYVAULT:** (Applicable only if using pipelines to  create VMs) The VMs getting provisoned as part of the pipelines uses the secret stored in a pre-created AzureKeyvault for setting up the admin/root credentials. Ensure that there is a keyvault present in the environment which the Service connection can access.
2. **KEYVAULT Reference** (Applicable only if using pipelines to  create VMs) Ensure that the *.parameters.json file for windows and linux vms are updated with the keyvault ID and the secret name. 
>>> ![image.png](/.attachments/image-608dcea4-3550-4e5c-b90c-af373c5d71c8.png)



# Starter Repo Structure

- **ARM** - This folder contains the Azure Resource Manager Templates for creating different Azure Resources. The templates are grouped into subfolders for respective resources like vnets, subnets etc. 
- [x] **.deploy.json* - The deployment file which has the configuration information for the resource to be created. 
- [x] **.parameters.json* - The parameters file, which has the required parameters for the deployment. 


- **Terraform** -  This folder contains the Terraform manifests for creating different Azure Resources. The manifests are grouped into subfolders for respective resources like vnets, subnets etc. 
- [x] *main.tf* - The deployment file which has the configuration information for the resource to be created. 
- [x] *variables.tf* - The variables file, which has the required parameters for the deployment.

- **Pipelines** - 
- [x] *ARM.pipeline.yaml* - The multistage yaml pipeline definition for deploying resources selectively using the ARM Template artifacts. 
- [x] *Terraform.pipeline.yaml* - The multistage yaml pipeline definition for deploying resources using the Terraform artifacts. 


# Deploy IaC locally (outside the pipelines)


###ARM Templates
The following steps explain how to deploy an ARM template into the target Azure subscription via PowerShell. Ensure that you have the **[Az modules](https://docs.microsoft.com/en-us/powershell/azure/new-azureps-module-az?view=azps-5.8.0)** installed in Powershell

1. Sign in to Azure portal from Powershell and select target Azure subscription
> ```
>Connect-AzAccount
>```
>```
>Set-AzContext [SubscriptionID/SubscriptionName]
>```

2. Create a resourcegroup (optional if youu already have a resource group to deploy resources into)
>```
>New-AzResourceGroup `
>  -Name myResourceGroup `
>  -Location "Central US"
>```
3. [Clone](https://docs.microsoft.com/en-us/azure/devops/repos/git/clone?view=azure-devops&tabs=visual-studio) the Starter IaC repository locally and modify the deploy.json and parameters.json files to match your deployment needs. 

4. Deploy the template via powershell 

>```powershell
>New-AzResourceGroupDeployment `
>  -Name blanktemplate `
>  -ResourceGroupName myResourceGroup `
>  -TemplateFile vnet.deploy.json `
>  -TemplateParameterFile  vnet.parameters.json
>```

5. Validate the deployment by navigating to Azure portal and check the status in the **Deployments** Tab and checking if new resources are created as planned. 


> Detailed steps are available in this [**documentation**](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-create-first-template?tabs=azure-powershell)

###Terraform
The following steps explain how to deploy an terraform resources into the target Azure subscription via PowerShell. Ensure that you have the terraform utility installed and added to the system path. 

1. [Clone](https://docs.microsoft.com/en-us/azure/devops/repos/git/clone?view=azure-devops&tabs=visual-studio) the Starter IaC repository locally and modify the main.tf and variables.tf files to match your deployment needs. 

2. Follow the guidance in this [**document**](https://docs.microsoft.com/en-us/azure/developer/terraform/get-started-powershell) to deploy resources in Azure via Terraform.  All Terraform commands need to be executed in the directory where the .tf files are present for respective resources. 