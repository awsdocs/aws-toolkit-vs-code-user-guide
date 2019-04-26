# Setting Up the AWS Toolkit for Visual Studio Code<a name="setup-toolkit"></a>

This section describes how to install or upgrade the AWS Toolkit for Visual Studio Code\.

## Prerequisites<a name="setup-prereq"></a>

Before you can install the AWS Toolkit for Visual Studio Code, you must have the following:
+ **An Amazon Web Services account** – To obtain an AWS account, go to the [AWS home page](https://aws.amazon.com/), and choose **Sign Up Now**\. Signing up enables you to use all of the services offered by AWS\.
+ **A supported operating system** – The AWS Toolkit for Visual Studio Code is supported on Windows, Linux, macOS, and Unix\.
+ **VS Code version 1\.31\.1 or later** – We try to keep the AWS Toolkit for Visual Studio Code current with the default version that's available on the [VS Code download page](https://code.visualstudio.com/)\.
+ **AWS SAM CLI** – This is an AWS CLI tool that helps you to develop, test, and analyze your serverless applications locally\. This isn't required for installing the toolkit, but we recommend you install it because it's required for any AWS Serverless Application Model \(AWS SAM\) functionality\. See [Installing the AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html) in the *AWS Serverless Application Model Developer Guide*
+ **Docker** – This open\-source software container platform is required by the AWS SAM CLI\. For more information and download instructions, see [Docker](https://www.docker.com/)\. 

## Install the AWS Toolkit for Visual Studio Code<a name="setup-install"></a>

1. Start the VS Code integrated development environment \(IDE\)\.

1. Choose the **Extensions** icon in the **Activity Bar** on the side of VS Code to open the **Extensions** view\. This opens the VS Code Marketplace\.  
![\[The Extensions icon in the VS Code Activity Bar.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-extensions.png)

1. In the search box for **Extensions**, start typing **AWS** until the entry **AWS Toolkit for Visual Studio Code** is visible in the list\. Choose the entry to see its details in the right pane\.

1. In the right pane, choose **Install**\.

1. Once installed, if you're prompted to restart the IDE, choose **Restart** to finish installation\. \(This step might not be necessary for later versions of VS Code\.\)

After you install the AWS Toolkit for Visual Studio Code, you should configure your AWS [credentials](setup-credentials.md) to enable you to access your AWS resources from within VS Code\.