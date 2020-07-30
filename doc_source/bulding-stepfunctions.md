# Working with AWS Step Functions<a name="bulding-stepfunctions"></a>

You can use the AWS Toolkit for Visual Studio Code \(VS Code\) to perform various operations with [state machines](https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html)\.

**Topics**
+ [Prerequisites](#bulding-stepfunctions-pre)
+ [Work with state machines in VS Code](#starting-stepfunctions)
+ [State machine templates](#templates-stepfunctions)
+ [State machine graph visualization](#bulding-stepfunctions-visualizations)
+ [Code snippets](#bulding-stepfunctions-code-snippets)
+ [Code completion and validation](#bulding-stepfunctions-code-completion)

## Prerequisites<a name="bulding-stepfunctions-pre"></a>
+ Be sure your system meets the prerequisites specified in [Installing the Toolkit for VS Code](setup-toolkit.md#setup-prereq), then install the toolkit\.
+ Ensure that you have configured your credentials before opening the **AWS Explorer**\.

## Work with state machines in VS Code<a name="starting-stepfunctions"></a>

You can use VS Code to interact with remote state machines, and develop state machines locally\. You can create or update state machines, list existing state machines, execute them, and download them\. VS Code also lets you create new state machines from templates, see a visualization of your state machine, and provides code snippets, code completion, and code validation\.

### List existing state machines<a name="starting-sfn-list"></a>

If you've already created state machines, you can view a list of them:

1. Open the **AWS Explorer**\.

1. Select Step Functions

1. Verify that it lists all the state machines in your account\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_aws-explorer.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

### Download a state machine<a name="sfn-download"></a>

To download a state machine:

1. In the **AWS Explorer**, right click the state machine that you want to download\.

1. Select Download, then select the location where you want to download the state machine\.

1. Verify that it downloaded correctly\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_download.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

### Create a state machine<a name="starting-sfn-create"></a>

You can create a new state machine yourself, or you can use a template\. For more information on creating a state machine from a template, see the **State Machine Templates** section\. To create a new state machine:

1. Create a new [Amazon States Language](https://docs.aws.amazon.com/step-functions/latest/dg/concepts-amazon-states-language.html) \(ASL\) file with your state machine definition\. Use the menu at the bottom right to set it as Amazon States Language\.

1. Select **Publish to Step Functions**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_publish.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

1. Select **Quick Create**, choose a role, and name your state machine\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_publish_create_1.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_publish_create_2.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_publish_create_3.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

### Update a state machine<a name="starting-sfn-update"></a>

To update a state machine:

1. Edit the ASL file with your state machine definition\.

1. Select **Publish to Step Functions**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_publish.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

1. Select **Quick Update**, then select the state machine you want to update\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_publish_update_1.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_publish_update_2.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

### Execute a state machine<a name="starting-sfn-execute"></a>

To execute a state machine:

1. In the **AWS Explorer**, right click the state machine that you want to execute\.

1. Provide input for the execution\. You can try both input from a file, and input in a text box\.

1. Start the execution and verify that it runs successfully\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_start_execution_1.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_start_execution_2.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

## State machine templates<a name="templates-stepfunctions"></a>

When you create a state machine, you have the option to create it from a template\. The template contains a sample state machine definition with several commonly used states, and provides you with a starting point\. To use state machine templates:

1. Open the **Command Palette** in VS Code \.

1. Select **AWS: Create a new Step Functions state machine**\.

1. Choose the template you want to use\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_template_2.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

## State machine graph visualization<a name="bulding-stepfunctions-visualizations"></a>

Graph visualizations let you see what your state machine looks like in graphical format\. When you create a graph visualization, another tab will open and display a visualizion of the state machine JSON\. You can then compare the state machine definition you are writing concurrently with its visualization\. As you change your state machine definition, the visualization will be updated\.

**Note**  
To create a visualizion of a state machine definition, the definition must be open in the active editor\. If you close or rename the definition file, the visualization will close\.

To create a state machine graph visualization:

1. Define your state machine\.

1. Open the **Command Palette** in VS Code\.

1. To create a visualization, use the visualization button in the upper right corner, or choose **AWS Preview state machine graph**\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_code_and_graph.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

## Code snippets<a name="bulding-stepfunctions-code-snippets"></a>

Code snippets let you insert short sections of code\. To use code snippets:

1. Open a file and save it with the extension `.asl.json`\. 

1. Create a new state machine with the **States** property\.

1. Place the cursor within **States**\.

1. Use the key combination` Control + Space`, and select your preferred code snippet\.

1. Use `Tab` to traverse the variable and parameters in the code snippet\.

1. Test **Retry** and **Catch** snippets by placing the cursor within the related state\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_code_snippets.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

## Code completion and validation<a name="bulding-stepfunctions-code-completion"></a>

To see how code completion works:

1. Create several states\.

1. Place the cursor after a **Next**, **StartAt**, or **Default** property\.

1. Use the key combination` Control + Space` to list available completions\. Additional properties can be accessed using `Control + Space` again, and will be based on the `Type` of the `State`\.

1. As you work, code validation will happen for:
   + Missing properties
   + Incorrect values
   + No terminal state
   + Nonexistent states that are pointed to

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_code_completion_1.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sfn_code_completion_2.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/)