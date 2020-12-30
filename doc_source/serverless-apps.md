# Working with AWS Serverless Application<a name="serverless-apps"></a>

The AWS Toolkit for Visual Studio Code provides support for [serverless applications](https://aws.amazon.com/serverless/)\. Using the Toolkit for VS Code, you can create serverless applications that contain [AWS Lambda](https://aws.amazon.com/lambda/) functions, and then deploy the applications to an AWS CloudFormation stack\.

**Topics**
+ [Assumptions and prerequisites](#serverless-apps-assumptions)
+ [IAM permissions for serverless applications](#serverless-apps-permissions)
+ [Creating a new serverless application \(local\)](#serverless-apps-create)
+ [Opening a serverless application \(local\)](#serverless-apps-open)
+ [Running and debugging a serverless application from template \(local\)](#serverless-apps-debug)
+ [Deploying a serverless application to the AWS Cloud](#serverless-apps-deploy)
+ [Deleting a serverless application from the AWS Cloud](#serverless-apps-delete)
+ [Running and debugging Lambda functions directly from code](serverless-apps-run-debug-no-template.md)
+ [Running and debugging local Amazon API Gateway resources](debug-apigateway.md)
+ [Configuration options for debugging serverless applications](serverless-apps-run-debug-config-ref.md)
+ [Troubleshooting serverless applications](serverless-apps-troubleshooting.md)

## Assumptions and prerequisites<a name="serverless-apps-assumptions"></a>
+ Be sure that your system meets the required prerequisites specified in [Installing the AWS Toolkit for Visual Studio Code](setup-toolkit.md#setup-prereq)\.
+ Install the [AWS Serverless Application Model \(AWS SAM\)](https://docs.aws.amazon.com/serverless-application-model/) command line interface \(CLI\) and its prerequisites\. See **AWS SAM CLI** in the [setup prerequisites](setup-toolkit.md#setup-prereq)\. If Visual Studio Code is open when you perform these installations, you might need to close and reopen the editor\.
+ Identify your default AWS Region in your AWS config file\. For more information, see [Configuration and credential file settings](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html) in the *AWS Command Line Interface User Guide*\. If Visual Studio Code is open when you update your config file, you might need to close and reopen the editor\.
+ After installing your language SDK, be sure to [configure your toolchain](setup-toolchain.md)\.
+ To ensure that you can access the [CodeLens](https://code.visualstudio.com/api/language-extensions/programmatic-language-features#codelens-show-actionable-context-information-within-source-code) feature in AWS SAM template files, install the [YAML language support](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml) VS Code extension\.

## IAM permissions for serverless applications<a name="serverless-apps-permissions"></a>

In the Toolkit for VS Code you must have a credentials profile that contains the AWS Identity and Access Management \(IAM\) permissions necessary to deploy and run serverless applications\. You must have appropriate read/write access to the following services: AWS CloudFormation, IAM, Lambda, Amazon API Gateway, Amazon Simple Storage Service \(Amazon S3\), and Amazon Elastic Container Registry \(Amazon ECR\)\.

For information about ensuring that you have the necessary permissions to deploy and run serverless applications, see [Permissions](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/sam-permissions.html) in the *AWS Serverless Application Model Developer Guide*\. For information on how to set up your credentials profile, see [Setting up your AWS credentials](setup-credentials.md)\.

## Creating a new serverless application \(local\)<a name="serverless-apps-create"></a>

This procedure shows how to create a serverless application with the Toolkit for VS Code by using AWS SAM\. The output of this procedure is a local directory on your development host containing a sample serverless application, which you can build, locally test, modify, and deploy to the AWS Cloud\.

1. To open the **Command Palette**, choose **View**, **Command Palette**, and then enter **AWS**\.

1. Choose **AWS: Create new SAM Application**\.  
![\[Command palette dialog box.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-create-app-cmdlet.png)
**Note**  
If the AWS SAM CLI isn't installed, you get an error in the lower\-right corner of the VS Code editor\. If this happens, verify that you've met all the [assumptions and prerequisites](#serverless-apps-assumptions)\.

1. Choose the runtime for your AWS SAM application\.
**Note**  
If you select one of the runtimes with "\(Image\)", your application is package type `Image`\. If you select one of the runtimes without "\(Image\)", your application is type `Zip`\. For more information about the difference between `Image` and `Zip` package types, see [Lambda deployment packages](https://docs.aws.amazon.com/lambda/latest/dg/gettingstarted-package.html) in the *AWS Lambda Developer Guide*\.

1. Choose a location for your new project\. You can use an existing workspace folder if one is open, **Select a different folder** that already exists, or create a new folder and select it\. For this example, choose **There are no workspace folders open** to create a folder named `MY-SAM-APP`\.

1. Enter a name for your new project\. For this example, use `my-sam-app-nodejs`\. After you press **Enter**, the Toolkit for VS Code takes a few moments to create the project\.

When the project is created, your application is added to your current workspace\. You should see it listed in the **Explorer** window\.

## Opening a serverless application \(local\)<a name="serverless-apps-open"></a>

To open a serverless application on your local development host, open the folder that contains the application's template file\.

1. From the **File**, choose **Open Folder\.\.\.**\.

1. In the **Open Folder** dialog box, navigate to the serverless application folder that you want to open\.

1. Choose the **Select Folder** button\.

When you open an application's folder, it is added to the **Explorer** window\.

## Running and debugging a serverless application from template \(local\)<a name="serverless-apps-debug"></a>

You can use the Toolkit for VS Code to configure how to debug serverless applications and run them locally in your development environment\.

You start to configure debug behavior by using the VS Code [CodeLens](https://code.visualstudio.com/api/language-extensions/programmatic-language-features#codelens-show-actionable-context-information-within-source-code) feature to identify an eligible Lambda function\. CodeLens enables content\-aware interactions with your source code\. For information about ensuring that you can access the CodeLens feature, review the [Assumptions and prerequisites](#serverless-apps-assumptions) section from earlier in this topic\.

**Note**  
In this example, you debug an application that uses JavaScript\. However, you can use Toolkit for VS Code debugging features with the following languages and runtimes:  
C\# – \.NET Core 2\.1, 3\.1
JavaScript – Node\.js 10\.*x*, 12\.*x*
Python – 2\.7, 3\.6, 3\.7, 3\.8
Your language choice also affects how CodeLens detects eligible Lambda handlers\. For more information, see [Running and debugging Lambda functions directly from code](serverless-apps-run-debug-no-template.md)\.

In this procedure, you use the example application created in the [Creating a new serverless application \(local\)](#serverless-apps-create) section earlier in this topic\.

1. To view your application files in VS Code's File Explorer, choose **View**, **Explorer**\.

1. From the application folder \(for example, *my\-sample\-app*\), open the `template.yaml` file\.
**Note**  
If you use a template with a name that's different from `template.yaml`, the CodeLens indicator isn't automatically available in the YAML file\. This means that you must manually add a debug configuration\.

1. In the editor for `template.yaml`, go to the `Resources` section of the template that defines serverless resources\. In this case, this is the `HelloWorldFunction` resource of type `AWS::Serverless::Function`\.

   In the CodeLens indicator for this resource, choose **Add Debug Configuration**\.  
![\[Using the CodeLens indicator in the template.yaml file to add a debug configuration.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/yaml_template_debug.png)

1. In the **Command Palette**, select the runtime in which your AWS SAM application will run\.

1. In the editor for the `launch.json` file, edit or confirm values for the following configuration properties:
   + `"name"` – Enter a reader\-friendly name to appear in the **Configuration** drop\-down field in the **Run** view\.
   + `"target"` – Ensure that the value is `"template"` so that the AWS SAM template is the entry point for the debug session\.
   + `"templatePath"` – Enter a relative or absolute path for the `template.yaml` file\.
   + `"logicalId"` – Ensure that the name matches the one specified in the **Resources** section of the AWS SAM template\. In this case, it's the `HelloWorldFunction` of type `AWS::Serverless::Function`\.  
![\[Configuring the launch.json file for template-based debugging.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/template_based_config_updated.png)

   For more information about these and other entries in the `launch.json` file, see [Configuration options for debugging serverless applications](serverless-apps-run-debug-config-ref.md)\.

1. If you're satisfied with your debug configuration, save `launch.json`\. Then, to start debugging, choose the green "play" button in the **RUN** view\.

   When the debugging sessions starts, the **DEBUG CONSOLE** panel shows debugging output and displays any values returned by the Lambda function\. \(When debugging AWS SAM applications, the **AWS Toolkit** is selected as the **Output** channel in the **Output** panel\.\)

## Deploying a serverless application to the AWS Cloud<a name="serverless-apps-deploy"></a>

This example shows how to deploy the serverless application that created in the previous section \([Creating a new serverless application \(local\)](#serverless-apps-create)\) to the AWS Cloud using the Toolkit for VS Code\.

Before you perform a deployment, make sure that the following items are covered:
+ For applications with deployment type `Zip`, be sure to have a globally unique Amazon S3 bucket name to use for the deployment\.
+ For applications with deployment type `Image`, be sure to have both a globally unique Amazon S3 bucket name and an Amazon ECR repository URI to use for the deployment\.

For more information about Lambda package types, see [Lambda deployment packages](https://docs.aws.amazon.com/lambda/latest/dg/gettingstarted-package.html) in the *AWS Lambda Developer Guide*\.

To deploy a serverless application, follow these steps:

1. To open the **Command Palette**, choose **View**, **Command Palette**, and then enter **AWS**\.

1. Choose **AWS: Deploy SAM Application**\.  
![\[Command to deploy a serverless application.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-cmd.png)

1. Choose the `template.yaml` file to use for the deployment\.

1. Choose the AWS Region to deploy to\.

1. Enter the name of an Amazon S3 bucket that this deployment can use\. The bucket must be in the Region that you're deploying to\.
**Warning**  
The Amazon S3 bucket name must be globally unique across all existing bucket names in Amazon S3\. Therefore, you should add a unique identifier to the name given in the following example, or choose a different name\.

1. If your serverless application includes a function with package type `Image`, enter the name of an Amazon ECR repository that this deployment can use\. The repository must be in the Region that you're deploying to\.

1. Enter a name for the deployed stack, either a new stack name or an existing stack name\.

1. Verify the success of the deployment on the **OUTPUT** tab of VS Code\.

   If an error occurs, a message pops up in the lower\-right that is similar to the following:  
![\[An error pop-up while deploying a serverless application.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-error.png)

   If this happens, check the text in the **OUTPUT** tab for details\. The following is an example of error details:

   ```
   Error with child process: Unable to upload artifact HelloWorldFunction referenced by CodeUri parameter of HelloWorldFunction resource.
   S3 Bucket does not exist. Execute the command to create a new bucket
   aws s3 mb s3://pbart-my-sam-app-bucket
   An error occurred while deploying a SAM Application. Check the logs for more information by running the "View AWS Toolkit Logs" command from the Command Palette.
   ```

   In this example, the error occurred because the Amazon S3 bucket did not exist\.

   If an error occurs, you can also view the AWS Toolkit logs using the Command Palette\. To do this, go to the **View** menu, choose **Command Palette**, enter **AWS**, and choose **AWS: View AWS Toolkit Logs**\.

When the deployment is complete, you see your application listed in the **AWS Explorer**\. To learn how to invoke the Lambda function that was created as part of the application, see [Interacting with Remote Lambda Functions](remote-lambda.md)\.

## Deleting a serverless application from the AWS Cloud<a name="serverless-apps-delete"></a>

Deleting a serverless application involves deleting the AWS CloudFormation stack that you previously deployed to the AWS Cloud\. Note that this procedure does not delete your application directory from your local host\.

1. Open the [AWS Explorer](aws-explorer.md)\.

1. In the **AWS: Explorer** window, expand the Region containing the deployed application that you want to delete, and then expand **AWS CloudFormation**\.

1. Open the context \(right\-click\) menu for the name of the AWS CloudFormation stack that corresponds to the serverless application that you want to delete, and then choose **Delete AWS CloudFormation Stack**\.

1. To confirm that you want to delete the selected stack, choose **Yes**\.

If the stack deletion succeeds, the Toolkit for VS Code removes the stack name from the AWS CloudFormation list in **AWS Explorer**\.