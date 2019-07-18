# Creating a Serverless Application with the AWS Toolkit for Visual Studio Code<a name="create-sam"></a>

This example shows how to create a serverless application and then run and debug it using the AWS Toolkit for Visual Studio Code\.

## Prerequisites<a name="create-sam-prereq"></a>

\(In addition to those specified in the [Getting Started prerequisites](setup-toolkit.md#setup-prereq)\.\)
+ You need to have AWS SAM CLI and its prerequisites installed\. See **AWS SAM CLI** in the [setup prerequisites](setup-toolkit.md#setup-prereq)\.

  It would be a good idea to close Visual Studio Code before performing these installations\.
+ You need to identify your default AWS Region in your AWS config file\. For more information, see [Configuration and Credential Files](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html) in the *[AWS CLI User Guide](https://docs.aws.amazon.com/cli/latest/userguide/)*\. If Visual Studio Code is open when you update your config file, you might need to close and reopen the editor\.
+ After installing your language SDK, be sure to [Configure Your Toolchain](setup-toolchain.md)\.

## Create a Serverless Application with the Toolkit for VS Code<a name="create-serverless-app"></a>

This example shows how to create a serverless application with the Toolkit for VS Code by using the [AWS Serverless Application Model \(AWS SAM\)](https://docs.aws.amazon.com/serverless-application-model/)\.

1. To open the **Command Palette**, choose **View**, **Command Palette**, and then enter **AWS**\.

1. Choose **AWS: Create new SAM Application**\.  
![\[Command palette dialog box.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-cmdlet.png)
**Note**  
If the AWS SAM CLI is not installed, you will get an error in the lower\-right corner of VS Code\. If this happens, see the [prerequisites](#create-sam-prereq) described earlier\.

1. Choose the runtime for your SAM application\. For this example, choose **nodejs10\.x**\.  
![\[Screenshot of the runtime selection list.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-runtime.png)

1. Choose a location for your new project\. You can use an existing location or use **Choose a different folder** to create a location\. For this example, create a folder named `MY-SAM-APP`\.  
![\[Screenshot of the location selection dialog box.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-location.png)

1. Enter a name for your new project\. For this example, use `my-sam-app-nodejs`\. After you press **Enter**, the Toolkit for VS Code takes a few moments to create the project\.  
![\[Screenshot of the dialog box to enter a name for the SAM project.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-name.png)

Once the project is created, your application is added to your current workspace\. You will see it listed in the **Explorer** window\.

![\[Screenshot of the explorer with your new project.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-explorer.png)

## Run and Debug Your Serverless Application<a name="run-debug-sam-app"></a>

After the AWS SAM application is created, you can use [CodeLenses](https://code.visualstudio.com/blogs/2017/02/12/code-lens-roundup) to run and debug the application\.

1. From the `hello-world` directory in the project explorer, open `app.js`, if it is not already open\.  
![\[app.js file location in the AWS SAM project.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-app-file.png)

1. Select the **Run Locally** CodeLens\.
**Note**  
To supply event information, select the **Configure** link from the CodeLens line in your code, as shown in the following screenshot\.  
![\[CodeLens Menu\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-codelens-menu.png)

   If the CodeLenses are not visible, select the **AWS Explorer** icon in the **Activity Bar** to activate them\.  
![\[AWS Explorer Icon\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-explorer-icon.png)

1. After the local run is complete, the **OUTPUT** tab or the **TERMINAL** tab will show the output\.  
![\[Output of running the application locally.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-run-locally.png)
**Note**  
For Windows users: If you encounter a Docker mounting error during this process, you might need to refresh the credentials for your shared drives \(in Docker Settings\)\. A Docker mounting error might something like the following:  

   ```
   Fetching lambci/lambda:nodejs10.x Docker container image......
   2019-07-12 13:36:58 Mounting C:\Users\<username>\AppData\Local\Temp\ ... as /var/task:ro,delegated inside runtime container
   Traceback (most recent call last):
   ...
   requests.exceptions.HTTPError: 500 Server Error: Internal Server Error ...
   ```

1. Choose the **Debug Locally** CodeLens to debug your application\. When in debug mode, you can set breakpoints, step through each line, inspect variables and change values just as you would for any other application\.