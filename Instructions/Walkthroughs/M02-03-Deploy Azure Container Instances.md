---
wts:
    title: '03 - Deploy Azure Container Instances (10 min)'
    module: '02 - Azure Architecture & Services'
---

# 03 - Deploy Azure Container Instances (10 min)

In this walkthrough we create, configure, and deploy a container by using Azure Container Instances (ACI) in the Azure Portal. The container is a Welcome to ACI web application that displays a static HTML page. 

# Task 1: Create a container instance 

In this task, we will create a new container instance for the web application.  

1. Sign in to the [Azure portal](https://portal.azure.com).

2. From the **All services** blade, search for and select **Container instances** and then click **+ Create**. 

3. Provide the following Basic details for the new container instance  (leave the defaults for everything else)): 

	| Setting| Value|
	|----|----|
	| Subscription | ***Use default supplied*** |
	| Resource group | Click on **Create new** <br /> Name: **03-myACIApp** |
	| Container name| **mycontainer**|
	| Region | **(US) East US** |
	| Availability Zones | **None** |
	| SKU | **Standard** |
	| Image source| **Quickstart images**|
	| Image| **mcr.microsoft.com/azuredocs/aci-helloworld:latest (Linux)**|
	| Size| ***Leave at the default***|


4. Configure the Networking tab (replace **xxxxx** with letters and digits such that the name is globally unique). Leave all other settings at their default values.

	| Setting| Value|
	|--|--|
	| DNS name label| **mycontainerdnsxxxxx** |
	| DNS name label scope| **Tenant** |

	
	**Note**: Your container will be publicly reachable at dns-name-label.region.azurecontainer.io. If you receive a **DNS name label not available** error message following the deployment, specify a different DNS name label (replacing the xxxxx) and re-deploy. 

5. Click **Review and Create** to start the automatic validation process.

6. Click **Create** to create the container instance. 

7. Monitor the deployment page and the **Notifications** page. 


# Task 2: Verify deployment of the container instance

In this task, we verify that the container instance is running by ensuring that the welcome page displays.

1. After the deployment is complete, click the **Go to resource** link the deployment blade or the link to the resource in the Notification area.

2. On the **Overview** blade of **mycontainer**, ensure your container **Status** is **Running**. 

3. Locate the Fully Qualified Domain Name (FQDN).

	![Screenshot of the overview pane for the newly created container in Azure portal, with the FQDN highlighted. ](../images/M02-0301.png)

4. Copy the container's FQDN into a new web browser tab and press **Enter**. The Welcome page should display. If the web page cannot be opened, you should wait up to 4 minutes. 
	>**Important**: The deployment can take up to 4 minutes. 

	![Screenshot of the ACI welcome message shown in a web browser.](../images/M02-0302.png)


**Congratulations!** You have used Azure Portal to successfully deploy an application to a container in Azure Container Instances.

**Note**: To avoid additional costs, you can optionally remove this resource group. Search for resource groups, click your resource group, and then click **Delete resource group**. Verify the name of the resource group and then click **Delete**. Monitor the **Notifications** to see how the delete is proceeding.
