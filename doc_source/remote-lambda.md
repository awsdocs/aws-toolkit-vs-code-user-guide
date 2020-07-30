# Interacting with Remote Lambda Functions<a name="remote-lambda"></a>

Using the Toolkit for VS Code, you can interact with [AWS Lambda](https://aws.amazon.com/lambda/) functions in various ways, as described later in this topic\.

For more information about Lambda, see the [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/)\. 

**Note**  
If you have already created Lambda functions by using the AWS Management Console or in some other way, you can invoke them from the Toolkit\. To create a new function \(using VS Code\) that you can deploy to AWS Lambda, you must first [create a serverless application](create-sam.md)\.

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
Do not use this procedure to delete Lambda functions that are associated with [AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/) \(for example, the Lambda function that was created when [creating a serverless application](create-sam.md) earlier in this guide\)\. These functions must be deleted through the AWS CloudFormation stack\.

****

1. In the **AWS Explorer**, choose the name of the Lambda function you want to delete, and then open its context menu\.  
![\[Context menu for Lambda function.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-func-delete-menu.png)

1. Choose **Delete**\.

1. In the message that appears, choose **Yes** to conﬁrm the delete\.  
![\[Delete Lambda confirmation dialog box\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-delete-confirm.png)

After the function is deleted, it's no longer listed in the **AWS Explorer**\.