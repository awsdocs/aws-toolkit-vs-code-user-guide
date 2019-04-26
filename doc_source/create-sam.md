# Creating a Serverless Application<a name="create-sam"></a>

This example shows how to create a serverless application and then run and debug it using the AWS Toolkit for Visual Studio Code\.

## Create a Serverless Application with the AWS Toolkit for Visual Studio Code<a name="create-serverless-app"></a>

 This example shows how to create a serverless application with the AWS Toolkit for Visual Studio Code using the AWS Serverless Application Model \(AWS SAM\)\. 

1. Open the **Command Palette** in the VS Code and enter **AWS**\.

1. Choose **AWS Create new SAM Application**\.  
![\[Command palette dialog box.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-cmdlet.png)

1. Choose the runtime for your SAM application\. For this example, choose nodejs8\.10\.  
![\[Screenshot of the runtime selection list.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-runtime.png)

1. Choose a location for your new project\. You can choose an existing location or choose **Browse** to create a new location\.  
![\[Screenshot of the location selection dialog.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-location.png)

1. Enter a name for your new project\.  
![\[Screenshot of the dialog to enter a name for the SAM project.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-name.png)

Once the project is created, your application is added to your current workspace\. You will see it listed in the **Explorer** window\.

![\[Screenshot of the explorer with your new project.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-explorer.png)

## Run and Debug your AWS SAM application<a name="run-debug-sam-app"></a>

After the AWS SAM application is created, you can use [CodeLenses](https://code.visualstudio.com/blogs/2017/02/12/code-lens-roundup) to run and debug the application\.

1. Open the `app.js` file \(in the hello\-world directory\) from the project explorer\.  
![\[app.js file location in the AWS SAM project.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-app-file.png)

1. If the **CodeLenses** are not already visible, select the AWS Explorer icon in the Activity Bar to activate it\.  
![\[CodeLens menu.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-codelens-menu.png)

1. Choose **Run Locally**\. The terminal will show the output of the local run\.  
![\[Output of running the application locally.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-run-locally.png)

1. Choose **Debug Locally** to debug your application\. When in debug mode, you can set breakpoints, step through each line, inspect variables and change values just as you would for any other application\. 