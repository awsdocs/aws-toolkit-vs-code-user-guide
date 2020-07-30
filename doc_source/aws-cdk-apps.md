# Working with AWS CDK applications<a name="aws-cdk-apps"></a>


****  

|  | 
| --- |
| This is prerelease documentation for a feature in preview release\. It is subject to change\. | 

Use the **AWS CDK Explorer** in the AWS Toolkit for VS Code to visualize and work with AWS CDK applications\.

## Prerequisites<a name="aws-cdk-apps-prereq"></a>
+ Be sure your system meets the the prerequisites specified in [Installing the Toolkit for VS Code](setup-toolkit.md#setup-prereq)\.
+ Install the AWS CDK command line interface, as described in the first few sections of [Getting Started with the AWS CDK](https://docs.aws.amazon.com/cdk/latest/guide/getting_started.html) in the *AWS Cloud Development Kit \(AWS CDK\) Developer Guide*\.
**Important**  
The AWS CDK version must be 1\.17\.0 or later\. Use **`cdk --version`** on the command line to see what version you're running\.

## Visualize an AWS CDK application<a name="aws-cdk-apps-visualize"></a>

Using the **AWS CDK Explorer**, you can create a CDK app or load an existing one\. Then, you can visualize the [stacks](https://docs.aws.amazon.com/cdk/latest/guide/stacks.html) and [resources](https://docs.aws.amazon.com/cdk/latest/guide/resources.html) that are defined in the CDK constructs of that app\.

Perform the first several steps of the [Hello World Tutorial](https://docs.aws.amazon.com/cdk/latest/guide/getting_started.html#hello_world_tutorial) in the *AWS CDK Developer Guide*\. Stop when you get to the step called **Deploying the Stack**\. You can run the commands provided in the tutorial, for example, **`mkdir`** and **`cdk init`**, on an operating system command line or in a **Terminal** window inside the VS Code editor\.

After you complete that first part of the CDK tutorial, load the resulting folder into the VS Code editor if it isn't already loaded\. At the bottom of the **VS Code Explorer** side bar find **AWS CDK Explorer**, and then open the app's tree view, as shown\.

![\[CDK Explorer tree view.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/cdk-tree-view.png)

The tree view gives you a visual representation of the information in the `tree.json` file of the CDK app, which is created when you run the **`cdk synth`** command\. The file is located in the app's `cdk.out` directory\.

### Important notes<a name="important-notes"></a>
+ When you load CDK apps into the VS Code editor, you can load multiple folders at one time\. Each folder can contain multiple CDK apps, as shown in the preceding image\. The AWS CDK Explorer finds apps in the project root directory and its direct subdirectories\.
+ When you perform the first several steps of the tutorial, you might notice that the last command you execute is **`cdk synth`**, which generates the `tree.json` file\. If you change aspects of a CDK app, for example, add more resources, you need to execute that command again to see the changes reflected in the tree view\.

## Perform other operations on an AWS CDK app<a name="aws-cdk-apps-other-tasks"></a>

You can use the VS Code editor to perform other operations on a CDK app, just as you would by using the command line of your operating system or other tools\. For example, you can update the code files in the editor and deploy the app by using a VS Code **Terminal** window\.

To try out these types of actions, use the VS Code editor to continue the [Hello World Tutorial](https://docs.aws.amazon.com/cdk/latest/guide/getting_started.html#hello_world_tutorial) in the *AWS CDK Developer Guide*\. Be sure to perform the last step, **Destroying the App's Resources**, so that you don't incur unexpected costs to your AWS account\.