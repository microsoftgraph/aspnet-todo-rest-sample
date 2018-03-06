# Microsoft Graph Excel REST API ASP.NET to-do list sample

This sample shows how to read and write into an Excel document stored in your OneDrive for Business account by using the Excel REST APIs.

## Prerequisites

This sample requires the following:  

  * [Visual Studio 2015](https://www.visualstudio.com/en-us/downloads) 
  * Either a [Microsoft account](https://www.outlook.com) or [work or school account](https://dev.office.com/devprogram)

## Register the application

1. Sign into the [Application Registration Portal](https://apps.dev.microsoft.com/) using either your personal or work or school account.

2. Choose **Add an app**.

3. Enter a name for the app, and choose **Create application**. 
	
   The registration page displays, listing the properties of your app.

4. Copy the Application Id. This is the unique identifier for your app. 

5. Under **Application Secrets**, choose **Generate New Password**. Copy the password from the **New password generated** dialog.

   You'll use the application ID and password (secret) to configure the sample app in the next section. 

6. Under **Platforms**, choose **Add Platform**.

7. Choose **Web**.

8. Make sure the **Allow Implicit Flow** check box is selected, and enter *http://localhost:21942/* as the Redirect URI. 

   The **Allow Implicit Flow** option enables the hybrid flow. During authentication, this enables the app to receive both sign-in info (the id_token) and artifacts (in this case, an authorization code) that the app can use to obtain an access token.

9. Choose **Save**.

## Configure the app
1. Open **Microsoft-Graph-ExcelRest-ToDo.sln** file. 
2. In Solution Explorer, open the **Web.config** file. 
3. Replace *ENTER_YOUR_CLIENT_ID* with the client ID of your registered Azure application.
4. Replace *ENTER_YOUR_SECRET* with the key of your registered Azure application.

## Run the app

1. Press F5 to build and debug. Run the solution and sign in with your organizational account. The application launches on your local host and shows the starter page. 
![Graph and AAD authentication starter page](images/ExcelApp.jpg)
     > Note: Copy and paste the start page URL address **http://localhost:21942/home/index** to a different browser if you get the following error during sign in: **AADSTS70001: Application with identifier ad533dcf-ccad-469a-abed-acd1c8cc0d7d was not found in the directory**.
2. Choose the `Click here to sign in` button in the middle of the page or the `Sign in` link at the top right of the page and authenticate with your Office 365 account. 
3. Select the `ToDoList` link from the top menu bar.
4. The application checks to see if a file named `ToDoList.xlsx` exists in the root OneDrive folder of your O365 account. If it doesn't find this file, it uploads a blank `ToDoList.xlsx` workbook and adds all of the necessary tables, columns, and rows, along with a chart. After finding or uploading and configuring the workbook, the application then displays the task list page. If the workbook contains no tasks, you'll see an empty list.
5. If you're running the application for the first time, you can verify that the application uploaded and configured the `ToDoList.xlsx` file by navigating to **https://yourtenant.sharepoint.com**, clicking on the App Launcher "Waffle" at the top left of the page, and then choosing the OneDrive application. You'll see a file named **ToDoList.xlsx** in the root directory, and when you click on the file, you'll see worksheets named **ToDoList** and **Summary**. The **ToDoList** worksheet contains a table that lists each "to-do" item, and the **Summary** worksheet contains a summary table and a chart.
6. Select the `Add New' link to add a new task. Fill in the form with the task details.
7. After you add a task, the app shows the updated task listing. If the newly added task isn't updated, choose the `Refresh` link after a few moments.
![Updated task listing](images/ToDoList.jpg)
8. Choose the `Charts' link to see the breakdown of tasks in a pie chart that was created and downloaded by using the Excel REST API.

![Breakdown of tasks in a pie chart](images/Chart.jpg)

<a name="contributing"></a>
## Contributing ##

If you'd like to contribute to this sample, see [CONTRIBUTING.MD](/CONTRIBUTING.md).

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Questions and comments

We'd love to get your feedback about the Microsoft Graph Excel REST API ASP.NET MVC sample. You can send your questions and suggestions to us in the [Issues](https://github.com/OfficeDev/Microsoft-Graph-ASPNET-ExcelREST-ToDo/issues) section of this repository.

Questions about Office 365 development in general should be posted to [Stack Overflow](http://stackoverflow.com/questions/tagged/MicrosoftGraph). Make sure that your questions or comments are tagged with [MicrosoftGraph].
  
## Additional resources

* [Microsoft Graph documentation](http://graph.microsoft.io)


## Copyright
Copyright (c) 2018 Microsoft. All rights reserved.
