# Deleting an AWS CloudFormation Stack<a name="cloudformation-delete"></a>

Using the AWS Toolkit for Visual Studio Code, you can delete AWS CloudFormation stacks\.

## Prerequisites<a name="cloudformation-delete-prereq"></a>

\(In addition to those specified in the [Getting Started prerequisites](setup-toolkit.md#setup-prereq)\.\)
+ The AWS credentials that you configured in [Setting Up Your AWS Credentials](setup-credentials.md) must include appropriate read\-write access to the AWS CloudFormation service\. If, in the **AWS Explorer**, under **CloudFormation**, you see a message similar to "Error loading CloudFormation resources", check the permissions attached to those credentials\. Changes that you make to permissions will take a few minutes to affect the **AWS Explorer** in VS Code\.

## Delete a CloudFormation Stack<a name="delete-cf-stack"></a>

****

1. In the **AWS Explorer**, open the context menu of the AWS CloudFormation stack you want to delete\.  
![\[Delete Cloudformation context menu.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/cfn-delete-menu.png)

1. Choose **Delete CloudFormation Stack**\.

1. Choose **Yes** to conﬁrm the delete\.  
![\[Delete confirmation message.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/cfn-delete-confirm.png)

After the stack is deleted, you'll no longer see it listed in the **AWS Explorer**\.