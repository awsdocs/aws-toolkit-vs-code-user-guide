# Interacting with Remote Lambda Functions<a name="remote-lambda"></a>

Using the Toolkit for VS Code, you can interact with [AWS Lambda](https://aws.amazon.com/lambda/) functions in various ways, as described later in this topic\.

For more information about Lambda, see the [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/)\. 

**Note**  
If you have already created Lambda functions by using the AWS Management Console or in some other way, you can invoke them from the Toolkit\. To create a new function \(using VS Code\) that you can deploy to AWS Lambda, you must first [create a serverless application](serverless-apps.md#serverless-apps-create)\.

**Topics**
+ [Prerequisites](#remote-lambda-prereq)
+ [Invoke a Lambda Function](#invoke-lam-func)
+ [Delete a Lambda Function](#delete-lambda)
+ [Import a Lambda Function](#import-lambda)
+ [Upload a Lambda Function](#upload-lambda)

## Prerequisites<a name="remote-lambda-prereq"></a>
+ Be sure your system meets the the prerequisites specified in [Installing the Toolkit for VS Code](setup-toolkit.md#setup-prereq)\.
+ Ensure that the credentials you configured in [Establishing credentials](establish-credentials.md) include appropriate read/write access to the AWS Lambda service\. If in the **AWS Explorer**, under **Lambda**, you see a message similar to "Error loading Lambda resources", check the permissions attached to those credentials\. Changes that you make to permissions will take a few minutes to affect the **AWS Explorer** in VS Code\.

## Invoke a Lambda Function<a name="invoke-lam-func"></a>

You can invoke a Lambda function on AWS from the Toolkit for VS Code\.

****

1. In the **AWS Explorer**, choose the name of the Lambda function you want to invoke, and then open its context menu\.  
![\[Context menu for Lambda function.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-func-invoke-menu.png)

1. Choose **Invoke on AWS**\.

1. In the invoke window that opens, enter the input that your Lambda function needs\. The Lambda function might, for example, require a string as an input, as shown in the text box\.  
![\[Field for entering Lambda input as text.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-run-input.png)

You'll see the output of the Lambda function just like you would for any other project using VS Code\.

![\[Output of Lambda function running.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-run-output.png)

## Delete a Lambda Function<a name="delete-lambda"></a>

You can also delete a Lambda function using the same context menu\.

**Warning**  
Do not use this procedure to delete Lambda functions that are associated with [AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/) \(for example, the Lambda function that was created when [creating a serverless application](serverless-apps.md#serverless-apps-create) earlier in this guide\)\. These functions must be deleted through the AWS CloudFormation stack\.

****

1. In the **AWS Explorer**, choose the name of the Lambda function you want to delete, and then open its context menu\.  
![\[Context menu for Lambda function.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-func-delete-menu.png)

1. Choose **Delete**\.

1. In the message that appears, choose **Yes** to conﬁrm the delete\.  
![\[Delete Lambda confirmation dialog box\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-delete-confirm.png)

After the function is deleted, it's no longer listed in the **AWS Explorer**\.

## Import a Lambda Function<a name="import-lambda"></a>

You can import code from a remote Lambda funcion into your VS Code workspace for editing and debugging\.

**Note**  
 The toolkit only supports importing Lambda functions using supported Node\.js and Python runtimes\. 

1.  In the **AWS Explorer**, choose the name of the Lambda function you want to import, then open its context menu\. 

1.  Choose **Import\.\.\.** 

1.  Choose a folder to import the Lambda code to\. Folders outside the current workspace will be added to your current workspace\. 

1.  After download, the Toolkit adds the code to your workspace and opens the file containing the Lambda handler code\. The Toolkit also creates a *launch configuration*, which appears in the VS Code run panel so you can locally run and debug the Lambda function using AWS Serverless Application Model\. For more information about using AWS SAM, see [Running and debugging a serverless application from template \(local\)](serverless-apps.md#serverless-apps-debug)\. 

## Upload a Lambda Function<a name="upload-lambda"></a>

You can update existing Lambda functions with local code\. Updating code in this way does not use the AWS SAM CLI for deployment and does not create an AWS CloudFormation stack\. This functionality can upload a Lambda function with any runtime supported by Lambda\.

**Warning**  
 The toolkit can't check whether your code works\. Make sure the code works before updating production Lambda functions\. 

1.  In the **AWS Explorer**, choose the name of the Lambda function you want to import, then open its context menu\. 

1.  Choose **Upload Lambda\.\.\.** 

1.  Choose from the three options for uploading your Lambda function\. The options include: 

**Upload a premade \.zip archive**
   + Choose **Zip Archive** from the Quick Pick menu\.
   + Choose a \.zip file from your file system and confirm the upload with the modal dialog\. This uploads the \.zip file as is and immediately updates the Lambda following deployment\.

**Upload a directory as is**
   + Choose **Directory** from the Quick Pick menu\.
   + Choose a directory from your file system\.
   + Choose **No** when prompted to build the directory, then confirm the upload with the modal dialog\. This uploads the directory as is and immediately updates the Lambda following deployment\.

**Build and upload a directory**
**Note**  
This requires the AWS SAM CLI\.
   + Choose **Directory** from the Quick Pick menu\.
   + Choose a directory from your file system\.
   + Choose **Yes** when prompted to build the directory, then confirm the upload with the modal dialog\. This builds the code in the directory using the AWS SAM CLI `sam build` command and immediately updates the Lambda following deployment\.
**Note**  
The toolkit will warn you if it can't detect a matching handler prior to upload\. If you wish to change the handler tied to the Lambda function, you can do so through the AWS Management Console or the AWS CLI\.