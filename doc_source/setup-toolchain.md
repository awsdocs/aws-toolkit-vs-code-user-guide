# Configuring your toolchain<a name="setup-toolchain"></a>

The AWS Toolkit for Visual Studio Code supports multiple languages that you can use to interact with AWS\. This topic describes how to set up the toolchain for each of these languages\.

## Configure a toolchain for \.NET Core<a name="setup-toolchain-for-net"></a>

1. Ensure that you have the Toolkit for VS Code [installed](setup-toolkit.md#setup-install)\.

1. Install the [C\# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)\. This extension enables VS Code to debug \.NET Core applications\.

1. Open an AWS Serverless Application Model \(AWS SAM\) application, or [create one](create-sam.md#create-serverless-app)\.

1. Open the folder that contains `template.yaml`\.

## Configure a toolchain for Node\.js<a name="setup-toolchain-for-node"></a>

1. Ensure that you have the Toolkit for VS Code [installed](setup-toolkit.md#setup-install)\.

1. Open an AWS SAM application, or [create one](create-sam.md#create-serverless-app)\.

1. Open the folder that contains `template.yaml`\.

## Configure a toolchain for Python<a name="setup-toolchain-for-python"></a>

1. Ensure that you have the Toolkit for VS Code [installed](setup-toolkit.md#setup-install)\.

1. Install the [Python extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-python.python)\. This extension enables VS Code to debug Python applications\.

1. Open an AWS SAM application, or [create one](create-sam.md#create-serverless-app)\.

1. Open the folder that contains `template.yaml`\.

1. Open a terminal at the root of your application, and configure `virtualenv` by running `python -m venv ./.venv`\.
**Note**  
You only need to configure `virtualenv` once per system\.

1. Activate `virtualenv` by running one of the following:
   + Bash shell: `./.venv/Scripts/activate`
   + PowerShell: `./.venv/Scripts/Activate.ps1`

## Using Your toolchain<a name="use-toolchain"></a>

Once you have your toolchain set up, you can use it to [run or debug](run-debug-sam-app.md) the AWS SAM application\.