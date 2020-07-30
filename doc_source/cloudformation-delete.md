# Deleting an AWS CloudFormation stack<a name="cloudformation-delete"></a>

You can use the AWS Toolkit for Visual Studio Code to delete AWS CloudFormation stacks\.

## Prerequisites<a name="cloudformation-delete-prereq"></a>
+ Be sure your system meets the the prerequisites specified in [Installing the Toolkit for VS Code](setup-toolkit.md#setup-prereq)\.
+ Ensure that the credentials you configured in [Establishing credentials](establish-credentials.md) include appropriate read/write access to the AWS CloudFormation service\. If in the **AWS Explorer**, under **CloudFormation**, you see a message similar to "Error loading CloudFormation resources", check the permissions attached to those credentials\. Changes that you make to permissions will take a few minutes to affect the **AWS Explorer** in VS Code\.

## Delete a CloudFormation stack<a name="delete-cf-stack"></a>

****

1. In the **AWS Explorer**, open the context menu of the AWS CloudFormation stack you want to delete\.  
![\[Delete Cloudformation context menu.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/cfn-delete-menu.png)

1. Choose **Delete CloudFormation Stack**\.

1. In the message that appears, choose **Yes** to conﬁrm the delete\.  
![\[Delete confirmation message.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/cfn-delete-confirm.png)

After the stack is deleted, it's no longer listed in the **AWS Explorer**\.