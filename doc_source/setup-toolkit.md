# Installing the AWS Toolkit for Visual Studio Code<a name="setup-toolkit"></a>

This section describes how to install the AWS Toolkit for Visual Studio Code\.

## Prerequisites<a name="setup-prereq"></a>

### Required<a name="setup-prereq-req"></a>

Before you can install the Toolkit for VS Code, you must have the following:
+ **An Amazon Web Services account** – To obtain an AWS account, go to the [AWS home page](https://aws.amazon.com/)\. Choose **Create an AWS Account**, or **Complete Sign Up** \(if you've visited the site before\)\. Signing up enables you to use all of the services that AWS offers\.
+ **A supported operating system** – The Toolkit for VS Code is supported on Windows, Linux, and macOS\.
+ **VS Code version 1\.31\.1 or later** – We try to keep the Toolkit for VS Code current with the default version that's available on the [VS Code download page](https://code.visualstudio.com/)\.

### Optional<a name="setup-prereq-opt"></a>

Before you can use certain features of the Toolkit for VS Code, you must have the following:
+ **Code Development** – The relevant SDK for the language that you want to use\. You can download from the following links, or use your favorite package manager:
  + \.NET SDK: [https://dotnet.microsoft.com/download](https://dotnet.microsoft.com/download)
  + Node\.js SDK: [https://nodejs.org/en/download](https://nodejs.org/en/download)
  + Python SDK: [https://www.python.org/downloads](https://www.python.org/downloads)
+ **AWS SAM CLI** – This is an AWS CLI tool that helps you develop, test, and analyze your serverless applications locally\. This isn't required for installing the toolkit\. However, we recommend that you install it \(and Docker, described next\) because it's required for any AWS Serverless Application Model \(AWS SAM\) functionality, such as [Creating serverless applications](create-sam.md)\.

  For more information, see [Installing the AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html) in the *[AWS Serverless Application Model Developer Guide](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/what-is-sam.html)*\.
+ **Docker** – The AWS SAM CLI requires this open\-source software container platform\. For more information and download instructions, see [Docker](https://www.docker.com/)\. 

## Install the Toolkit for VS Code<a name="setup-install"></a>

1. Start the VS Code editor\.

1. In the **Activity Bar** on the side of the VS Code editor, choose the **Extensions** icon\. This opens the **Extensions** view, which allows you to access the VS Code Marketplace\.  
![\[The Extensions icon in the VS Code Activity Bar.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-extensions.png)

1. In the search box for **Extensions**, search for **AWS Toolkit**\. Choose the entry to see its details in the right pane\.

1. In the right pane, choose **Install**\.

1. Once installed, if you're prompted to restart the editor, choose **Reload Required** to finish installation\.

After you install the Toolkit for VS Code, you should configure your [credentials](establish-credentials.md) to enable you to access your AWS resources from within VS Code\.