# Interacting with Remote Lambda Functions<a name="remote-lambda"></a>

## Invoke a Lambda Function<a name="invoke-lam-func"></a>

You can invoke a Lambda function on AWS from the AWS Toolkit for Visual Studio Code\.

****

1. In the **AWS Explorer**, choose the name of the Lambda function to invoke to see the context menu\.  
![\[Lambda gutter icon\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-func-invoke-menu.png)

1. Choose **Invoke on AWS**\.

1. In the invoke window that opens, enter the input that your Lambda function needs\. The Lambda function used for this example requires a string as an input, as shown in the text box\.   
![\[Field for entering Lambda input as text.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-run-input.png)

You'll see the output of the Lambda function run just like you would for any other project using the VS Code\. 

![\[Output of Lambda function running.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-run-output.png)

## View Settings for a Remote Lambda Function<a name="view-lambda-configs"></a>

You can view configuration and policy settings for remote Lambda functions by selecting the appropriate context menu\. 

1. In the **AWS Explorer**, choose the name of the Lambda function to see the context menu\.

1. Choose **Get Configuration**\.  
![\[Lambda configuration view.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-configuration.png)

1. Choose **Get Policy**\.  
![\[Lambda policy view.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-policy.png)

## Delete a Lambda Function<a name="delete-lambda"></a>

You can also delete the Lambda function using the same context menu\.

****

1. In the **AWS Explorer**, choose the name of the Lambda function to delete from the context menu\.  
![\[Lambda context menu\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-func-invoke-menu.png)

1. Choose **Delete**\.

1. In the message that appears, choose **Yes** to confirm the delete\.  
![\[Delete Lambda confirmation dialogue\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/lambda-delete-confirm.png)

Once the function is deleted, you will no longer see it listed in the **AWS Explorer**\.