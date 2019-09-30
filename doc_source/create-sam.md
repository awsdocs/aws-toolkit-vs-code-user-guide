# Creating a Serverless Application with the AWS Toolkit for Visual Studio Code<a name="create-sam"></a>

This example shows how to use the AWS Toolkit for Visual Studio Code to create a serverless application and then run and debug it\.

## Prerequisites<a name="create-sam-prereq"></a>
+ If you haven't already done so, satisfy the required prerequisites specified in [Installing the Toolkit for VS Code](setup-toolkit.md#setup-prereq)\.
+ In addition, install the AWS SAM CLI and its prerequisites\. See **AWS SAM CLI** in the [setup prerequisites](setup-toolkit.md#setup-prereq)\. If Visual Studio Code is open when you perform these installations, you might need to close and reopen the editor\.
+ Identify your default AWS Region in your AWS config file\. For more information, see [Configuration and Credential Files](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html) in the *[AWS CLI User Guide](https://docs.aws.amazon.com/cli/latest/userguide/)*\. If Visual Studio Code is open when you update your config file, you might need to close and reopen the editor\.
+ After installing your language SDK, be sure to [configure your toolchain](setup-toolchain.md)\.

## Create a Serverless Application with the Toolkit for VS Code<a name="create-serverless-app"></a>

This example shows how to create a serverless application with the Toolkit for VS Code by using the [AWS Serverless Application Model \(AWS SAM\)](https://docs.aws.amazon.com/serverless-application-model/)\.

1. To open the **Command Palette**, choose **View**, **Command Palette**, and then enter **AWS**\.

1. Choose **AWS: Create new SAM Application**\.  
![\[Command palette dialog box.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-cmdlet.png)
**Note**  
If the AWS SAM CLI isn't installed, you will get an error in the lower\-right corner of the VS Code editor\. If this happens, see the [prerequisites](#create-sam-prereq) described earlier\.

1. Choose the runtime for your SAM application\. For this example, choose **nodejs10\.x**\.  
![\[Screenshot of the runtime selection list.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-runtime.png)

1. Choose a location for your new project\. You can use an existing workspace folder if one is open, **Select a different folder** that already exists, or create a new folder and select it\. For this example, choose **There are no workspace folders open** to create a folder named `MY-SAM-APP`\.  
![\[Screenshot showing the location selection dialog box.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-location.png)

1. Enter a name for your new project\. For this example, use `my-sam-app-nodejs`\. After you press **Enter**, the Toolkit for VS Code takes a few moments to create the project\.  
![\[Screenshot showing the dialog box where you enter a name for the SAM project.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-name.png)

When the project is created, your application is added to your current workspace\. You should see it listed in the **Explorer** window\.

![\[Screenshot showing the Explorer showing your new project.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-explorer.png)

## Run and Debug Your Serverless Application<a name="run-debug-sam-app"></a>

After the AWS SAM application is created, you can use [CodeLens](https://code.visualstudio.com/blogs/2017/02/12/code-lens-roundup) indicators to run and debug the application\.

1. From the `hello-world` directory in the project explorer, open `app.js`, if it isn't already open\.  
![\[app.js file location in the AWS SAM project.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-app-file.png)

1. Select the **Run Locally** CodeLens indicator\.
**Note**  
To supply event information, select the **Configure** indicator from the CodeLens line in your code, as shown\.  
![\[CodeLens Menu\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-codelens-menu.png)

   If CodeLens indicators aren't visible, select the **AWS Explorer** icon in the **Activity Bar** to activate CodeLens\.  
![\[AWS Explorer icon\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-explorer-icon.png)

1. After the local run is complete, the output appears on the **OUTPUT** tab or the **TERMINAL** tab\.  
![\[Output of running the application locally.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-run-locally.png)
**Note**  
For Windows users, if you encounter a Docker mounting error during this process, you might need to refresh the credentials for your shared drives \(in Docker Settings\)\. A Docker mounting error might look something like the following\.  

   ```
   Fetching lambci/lambda:nodejs10.x Docker container image......
   2019-07-12 13:36:58 Mounting C:\Users\<username>\AppData\Local\Temp\ ... as /var/task:ro,delegated inside runtime container
   Traceback (most recent call last):
   ...
   requests.exceptions.HTTPError: 500 Server Error: Internal Server Error ...
   ```

1. Choose the **Debug Locally** CodeLens indicator to debug your application\. When in debug mode, you can set breakpoints, step through each line, inspect variables, and change values just as you would for any application\.