
Just as sample IaC repos, leveraging the inbuilt Starter CI/CD Pipelines also can significantly save time of Delivery team for smaller deployments.

| <span style="color:blue">However, for an extensive library of IaC code blocks to provision Azure resources in various patterns and combinations via different pre-configured pipelines, refer the **[Bootstrap guidance](/Packages/ACAI/ACAI-MO/Bootstrap-Template#Complete-Set-of-IAC-code-modules-&-Pipelines)** on how to leverage ACAI Domain's well maintained [IaCS repository](https://aka.ms/IaCS)</span> |
|--|

#Prerequisites
Before executing the starter pipelines there are some prerequisites to be configured. 

1. **Service Connection:** Ensure that the service connection for Azure RM called "MO-Bootstrap-ServiceConnection" is configured under project settings. (This is the connection used by the default starter pipelines)
2. **KEYVAULT:** (Applicable only if using pipelines to  create VMs) The VMs getting provisoned as part of the pipelines uses the secret stored in a pre-created AzureKeyvault for setting up the admin/root credentials. Ensure that there is a keyvault present in the environment which the Service connection can access.
3. **KEYVAULT Reference** (Applicable only if using pipelines to  create VMs) Ensure that the *.parameters.json file for windows and linux vms are updated with the keyvault ID and the secret name. 
>>> ![image.png](/.attachments/image-608dcea4-3550-4e5c-b90c-af373c5d71c8.png)

---
#Pipelines

For ACAI Bootstrap, we have included sample pipelines(single yaml) to automate continuous deployment of infrastructure resources to Azure. There are separate pipelines for ARM template deployment as well as Terraform Deployment (_currently under development_). The pipeline leverages the existing IaC codeblocks from the Start IaC Repository.

>![image.png](/.attachments/image-44d634c6-530d-4ebe-8852-1b8b985ef45e.png)

##Pipeline Structure 

The pipeline is configured as multistage, which will give you flexibility to decide which stages to be deployed selectively:

>![image.png](/.attachments/image-9cb2f8ca-8a10-4463-82fd-8e26dfeb8c88.png)

##Running the pipeline
###Steps:

1. Navigate to Pipelines under the project and select the pipeline you want to run (ARM or Terraform):
>>>![image.png](/.attachments/image-44d634c6-530d-4ebe-8852-1b8b985ef45e.png)
2. Click on Run Pipeline button 

>>>![image.png](/.attachments/image-0e16fcdf-2305-4864-af0e-d33af69d7e14.png)
3. Select the Operating System you want to deploy (Applicable only if you are deploying VMs. For subnets, Vnets etc, this choice is considered.) You can also change the branch for deployment if your updated IaC code is in a different branch. 
>>> ![image.png](/.attachments/image-b58c1999-8830-4ca8-8426-c8dcd7ca0027.png)
4. Optionally you can navigate to 'Stages to run' and select which stage/resource to deploy:
>>> ![image.png](/.attachments/image-f47d2b63-0e9b-4631-8088-d34cdcc38cab.png)
5. Now click on the Run button
>>> ![image.png](/.attachments/image-5da15c8e-fa01-4c89-81e9-bc2bf871f1d1.png)

You can validate the detailed status of each stage/job by navigating through the pipeline logs.  
> ![image.png](/.attachments/image-d901734c-3eed-4281-80c9-921a990f0c7f.png)
