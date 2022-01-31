# Introduction

Default Bootstrap ecosystem will be used for all delivery projects that are following Leading Edge Delivery Approach in ACAI Domain. This will help the project teams to start with predefined set of components available in the Azure Devops Project that can be easily leveraged for seamless project execution. Click [here](https://dev.azure.com/servicesdocs/DevOps/_wiki/wikis/LED%20Playbook/7934/Bootstrap) for more information regarding general Bootstarp guidance.

# Components

Following components would be deployed during the Bootstrap process:


<strong>Component | <strong>Details    |<strong>Remarks |
---------|-----------------------------|-----------------
<strong> Azure DevOps Project | Azure DevOps Project configured for your delivery team | N/A
<strong> Process template: | [CloudMoAgile Process Template](/Packages/ACAI/ACAI-MO/Bootstrap-Template/Process-Template) | The customized Agile Process Template to help ACAI Project teams achieve delivery efficiency, agility and quality for modernization projects.
<strong>Startup Work Items |  [Startup Work Items](/Packages/ACAI/ACAI-MO/Bootstrap-Template/Startup-Work-Items) | A simple list of PBIs that a team can use in order to ensure they have the essential foundational aspects of DevOps done | 
<strong> Starter Infra as Code Repository| [Starter IaC Repo](/Packages/ACAI/ACAI-MO/Bootstrap-Template/Starter-Infra-as-Code-Repo) | A Starter IaC repo available within the project to deploy foundational services like Vnet, Subnet, VMs etc using ARM templates or Terraform.
<strong>Starter Deployment Pipeline | [Starter Deployment Pipeline](/Packages/ACAI/ACAI-MO/Bootstrap-Template/Starter-Deployment-Pipeline-Guidance)| Environments are not provisioned by default to save cost. Delivery team members can leverage the existing Starter Deployment Pipelines to provision resources in Azure and modify the pipelines as needed. 
<strong>EasyInsights Dashboard | [EasyInsights Dashboard](/Packages/ACAI/ACAI-MO/Bootstrap-Template/EasyInsights-Dashboard)| Default Project level dashboard configured in EasyInsights instance managed by Services DevOps team. Provides standard project level dashboards using information from various data sources automatically captured depending on project configuration via an Azure DevOps extension.


#Complete Set of IAC code modules & Pipelines
The Bootstrap comes with a starter IaC repo and starter pipelines limited to some foundational Azure components only.  ACAI domain's infra-as-code-source (IaCS) solution
should be leveraged as a centralized, sanitized, reliable, high quality, modular, reusable and continuously maintained code base to deliver IaC projects (e.g. ACF, CCoE, AMO etc.). 

Please visit the following links for more information:

- [**IaCS Home Page**](https://aka.ms/iacs)

- **IaCS Repositories** - [**Components**](https://dev.azure.com/servicescode/infra-as-code-source/_git/Components) 

- **IaCS Repositories** -  [**Solutions**](https://dev.azure.com/servicescode/infra-as-code-source/_git/Solutions)

- **[IaCS Implementation Guide](https://dev.azure.com/servicescode/infra-as-code-source/_wiki/wikis/Wiki/3755/Implementation-Guide)**


*Note: Some of links mentioned in this page will work only for MSFT work accounts.*