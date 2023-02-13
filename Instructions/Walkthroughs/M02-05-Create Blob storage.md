---
wts:
    title: '05 - Create blob storage (5 min)'
    module: '02 - Azure Architecture & Services'
---
# 05 - Create blob storage (5 min)

In this walkthrough, we will create a storage account, then work with blob storage files.

# Task 1: Create a storage account 

In this task, we will create a new storage account. 

1. Sign in to the Azure portal at <a href="https://portal.azure.com" target="_blank"><span style="color: #0066cc;" color="#0066cc">https://portal.azure.com</span></a>

2. From the **All services** blade, search for and select **Storage accounts**, and then click **+ Create**. 

3. On the **Basics** tab of the **Create storage account** blade, fill in the following information (replace **xxxx** in the name of the storage account with letters and digits such that the name is globally unique). Leave the defaults for everything else.

    | Setting | Value | 
    | --- | --- |
    | Subscription | **Leave provided default** |
    | Resource group | Click on **Create new** <br /> Name: **05-storage-account** |
    | Storage account name | **storageaccountxxxxx** |
    | Location | **(US) East US**  |
    | Performance | **Standard** |
    | Redundancy | **Locally redundant storage (LRS)** |
    
    **Note** - Remember to change the **xxxxx** so that it makes a unique **Storage account name**

4. Click **Review** to review your storage account settings and allow Azure to validate the configuration. 

5. Once validated, click **Create**. Wait for the notification that the account was successfully created. 

6. From the Home page, search for and select **Storage accounts** and ensure your new storage account is listed.

    ![Screenshot of the newly created storage account in the Azure portal .](../images/M02-0501.png)

# Task 2: Work with blob storage

In this task, we will create a Blob container and upload a blob file. 

1. Click the name of the new storage account, scroll to **Containers** item in the menu on the left under the Data Storage section. 

2. Click **+ Container** and complete the information. Use the Information icons to learn more. When done click **Create**.


    | Setting | Value |
    | --- | --- |
    | Name | **container1**  |
    | Public access level| **Private (no anonymous access)** |
  

    ![Screenshot of the newly created blob container in the storage account in the Azure portal.](../images/M02-0502.png)

4. Open a new browser window and search **Bing** for an image of a flower. Right click on the image and save it to your VM. 

6. Back in the Portal, click on **container1** , and then select **Upload**.

5. Browse for the image file you just saved on your local computer. Select it and then select **open**.

   
6. Click the **Advanced** arrow, leave the default values but review the available options, and then click **Upload**.

    **Note**: You can upload as many blobs as you like in this way. New blobs will be listed within the container.

7. Once the file is uploaded, right-click on the file and notice the options including View/edit, Download, Properties, and Delete. 

8. If you have time review the options for Files, Tables, and Queues.

# Task 3: Monitor the storage account

1. Return to the storage account blade and click **Diagnose and solve problems**. 

2. Explore some of the most common storage problems. Notice there are multiple troubleshooters here.

3. On the storage account blade, scroll down to the **Monitoring** section and click **Insights**. Notice there is information on Failures, Performance, Availability, and Capacity. Your information will be different.

    ![Screenshot of the storage account Insights page.](../images/M02-0503.PNG)

Congratulations! You have created a storage account, then worked with storage blobs.

**Note**: To avoid additional costs, you can optionally remove this resource group. Search for resource groups, click your resource group, and then click **Delete resource group**. Verify the name of the resource group and then click **Delete**. Monitor the **Notifications** to see how the delete is proceeding.
