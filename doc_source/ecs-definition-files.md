# Using IntelliSense for Amazon ECS task\-definition files<a name="ecs-definition-files"></a>

One of the things that you might do when working with Amazon Elastic Container Service \(Amazon ECS\) is to create task definitions, as described in [Creating a Task Definition](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/create-task-definition.html) from the *Amazon Elastic Container Service Developer Guide*\. When you install the AWS Toolkit for Visual Studio Code, the installation includes IntelliSense functionality for Amazon ECS task\-definition files\.

## Prerequisites<a name="ecs-definition-files-prereq"></a>
+ Be sure your system meets the prerequisites specified in [Installing the Toolkit for VS Code](setup-toolkit.md#setup-prereq)\.

## Use IntelliSense in Amazon ECS task\-definition files<a name="ecs-definition-files-example"></a>

The following example shows you how you can take advantage of IntelliSense in Amazon ECS task\-definition files\.

1. Create a JSON file for your Amazon ECS task definition\. The file's name must have `ecs-task-def.json` at the end, but can have additional characters at the beginning\.

   For this example, create a file named `my-ecs-task-def.json`

1. Open the file in a VS Code editor and enter the initial curly braces\.

1. Enter the letter "c" as if you wanted to add `cpu` to the definition\. Observe the IntelliSense dialog that opens, which is similar to the following\.  
![\[IntelliSense dialog.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/ecs-task-def-intellisense.png)