# Working with AWS Services<a name="working-with-aws"></a>

The AWS Explorer gives you a view of the AWS services that the AWS Toolkit for Visual Studio Code can work with\. This section provides information about how to access and use the **AWS Explorer** in VS Code\. It assumes that you've already [installed and configured](getting-started.md) the Toolkit for VS Code on your system\.

**Note**  
If the toolkit has been installed and conﬁgured properly, you should see items in the **AWS Explorer**\. To see the **AWS Explorer**, choose the AWS icon in the **Activity bar**\.  
For example:  

![\[AWS Explorer with credentials defined.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-explorer-with-cred.png)
Note also that certain features require certain AWS permissions\. For example, to see the Lambda functions in your AWS account, the credentials you have configured in [Setting Up Your AWS Credentials](setup-credentials.md) must include at least read\-only Lambda permissions\. See the topics shown below for more specific information about the permissions that each feature needs\.

**Topics**
+ [Working with AWS Serverless Applications](serverless-apps.md)
+ [Working with AWS Lambda Functions](building-lambda.md)
+ [Working with AWS CloudFormation Stacks](cloudformation.md)