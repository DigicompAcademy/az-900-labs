---
wts:
    title: '10 - Implement Azure Functions (5 min)'
    module: '03: Management Tools & Automation'
---
# 10 - Implement Azure Functions (5 min)

In this walkthrough, we will create a Function App to display a Hello message when there is an HTTP request. 

# Task 1: Create a Function app 

In this task, we will create a Function app.

1. Sign in to the [Azure portal](https://portal.azure.com).

2. In the **Search** bar at the top of the portal, search for and select **Function App** and then, from the **Function App** blade, click **+ Create**.

3. Select the **Consumption** Hosting Plan. 

4. On the **Basic** tab of the **Function App** blade, specify the following settings (replace **xxxx** in the name of the function with letters and digits such that the name is globally unique and leave all other settings with their default values): 

    | Settings | Value |
    | -- | --|
    | Subscription | **Keep default supplied** |
    | Resource group | Click on **Create new** <br /> Name: **10-function** |
    | Function App name | **function-xxxx** |
    | Runtime stack | **Powershell Core** |
    | Version | **7.4** |
    | Region | **East US 2** |

    **Note** - Remember to change the **xxxx** so that it makes a unique **Function App name**

5. Click **Review + Create** and, after successful validation, click **Create** to begin provisioning and deploying your new Azure Function App.

6. Wait for the notification that the resource has been created.

7. When the deployment has completed, click **Go to resource** from the deployment blade. Alternatively, navigate back to the **Function App** blade, click **Refresh** and verify that the newly created function app has the **Running** status. 

    ![Screenshot of the Function App page with the new Function app.](../images/M03-1001.png)

# Task 2: Create a HTTP triggered function and test

In this task, we will use the Webhook + API function to display a message when there is an HTTP request. 

1. On the **Function App** blade, click the newly created function app. 

2. On the function app overview, Functions Tab click on **Create in Azure Portal**

    ![Screenshot of the choose a development environment step in the azure functions for dot net getting started pane inside Azure portal. The display elements for creating a new in-portal function are highlighted. The highlighted elements are expand the function app, add new function, in-portal, and the continue button.](../images/M03-1009.png)

3. An pop-up window will appear on the right. In the **Template** section click **HTTP trigger**. Click **Next** and **Create**. 

    ![Screenshot of the create a function step in the azure functions for dot net getting started pane inside Azure portal. The HTTP trigger card is highlighted to illustrate the display elements used to add a new webhook to an Azure function.](../images/M03-1010.png)

4. Test the function by clicking on **Test/Run**. Define a name with the corresponding value and click on **Run**. A message should then appear, e.g. **Hello, Test123. This HTTP triggered function executed successfully.**.  
       ![Test-Run](../images/M03-1011.png)

5. Click **Get function URL** from the top section of function editor and ensure to Copy the **default (Function Key)** value
   ![Get-Function-Key](../images/M03-1012.png)

6. Open a new browser tab and paste the copied function URL into your web browser's address bar. When the page is requested the function will run. Notice the returned message stating that the function requires a name in the request body.

    ![Screenshot of the please provide a name message.](../images/M03-1006.png)

7.  Append **&name=*yourname*** to the end of the URL.

    **Note**: For example, if your name is Cindy, the final URL will resemble the following: `https://azfuncxxx.azurewebsites.net/api/HttpTrigger1?code=X9xx9999xXXXXX9x9xxxXX==&name=cindy`

    ![Screenshot of a highlighted function URL and an appended example user name in the address bar of a web browser. The hello message and user name are also highlighted to illustrate the output of the function in the main browser window.](../images/M03-1007.png)

8.  When you hit enter, your function runs and every invocation is traced. To view the traces, return to the Portal **HttpTrigger1 \| Code + Test** and click **Logs**. You can open the **Logs** tab to get a live view. Open again the same URL as before. Now you should see an entry in the console. .

    ![Screenshot of a trace information log resulting from running the function inside the function editor in Azure portal.](../images/M03-1013.png) 

Congratulations! You have created a Function App to display a Hello message when there is an HTTP request.  

**Note**: To avoid additional costs, you can optionally remove this resource group. Search for resource groups, click your resource group, and then click **Delete resource group**. Verify the name of the resource group and then click **Delete**. Monitor the **Notifications** to see how the delete is proceeding.
