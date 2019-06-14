# Interacting with Remote Lambda Functions<a name="remote-lambda"></a>

Using the Toolkit for VS Code, you can interact with AWS Lambda functions is various ways\.

## Additional Prerequisites<a name="remote-lambda-prereq"></a>
+ The AWS credentials that you configured in [Setting Up Your AWS Credentials](setup-credentials.md) must include appropriate read\-write access to the AWS Lambda service\. If, in the **AWS Explorer** window, under **Lambda**, you see a message similar to "Error loading Lambda resources", check the permissions attached to those credentials\. Changes that you make to permissions will take a few minutes to affect the **AWS Explorer** window in VS Code\.

## Invoke a Lambda Function<a name="invoke-lam-func"></a>

You can invoke a Lambda function on AWS from the AWS Toolkit for Visual Studio Code\.

****

1. In the **AWS Explorer**, choose the name of the Lambda function you want to invoke and open its context menu\.  
![\[Context menu for Lambda function.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-func-invoke-menu.png)

1. Choose **Invoke on AWS**\.

1. In the invoke window that opens, enter the input that your Lambda function needs\. The Lambda function might, for example, require a string as an input, as shown in the text box\.  
![\[Field for entering Lambda input as text.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-run-input.png)

You'll see the output of the Lambda function run just like you would for any other project using VS Code\.

![\[Output of Lambda function running.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-run-output.png)

## Delete a Lambda Function<a name="delete-lambda"></a>

You can also delete the Lambda function using the same context menu\.

**Warning**  
Do not use this procedure to delete Lambda functions that are associated with [AWS CloudFormation](https://docs.aws.amazon.com//cloudformation/)\. These functions must be deleted through the AWS CloudFormation stack\.

****

1. In the **AWS Explorer**, choose the name of the Lambda function you want to delete and open its context menu\.  
![\[Context menu for Lambda function.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-func-delete-menu.png)

1. Choose **Delete**\.

1. Choose **Yes** to conﬁrm the delete\.  
![\[Delete Lambda confirmation dialogue\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-delete-confirm.png)

Once the function is deleted, you will no longer see it listed in the **AWS Explorer**\.