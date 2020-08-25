# Working with AWS Services in the AWS Explorer<a name="aws-explorer"></a>

The **AWS Explorer** gives you a view of some of the AWS services that you can work with when using the AWS Toolkit for Visual Studio Code\. See a high\-level view of the **AWS Explorer** in the [navigation](toolkit-navigation.md#aws-explorer-basic-ui) topic\.

 This section provides information about how to access and use the **AWS Explorer** in VS Code\. It assumes that you've already [installed and configured](setting-up.md) the Toolkit for VS Code on your system\.

Some important points:
+ If the toolkit is installed and conﬁgured correctly, you should see items in the **AWS Explorer**\. To see the **AWS Explorer**, choose the **AWS** icon in the **Activity bar**\.

  For example:  
![\[AWS Explorer with credentials defined.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-explorer-with-cred.png)
+ Certain features require certain AWS permissions\. For example, to see the AWS Lambda functions in your AWS account, the credentials you configured in [Establishing credentials](establish-credentials.md) must include at least read\-only Lambda permissions\. See the following topics for more information about the permissions that each feature needs\.

**Topics**
+ [Working with AWS Serverless Application](serverless-apps.md)
+ [Working with AWS CloudFormation stacks](cloudformation.md)
+ [Working with CloudWatch Logs by using the AWS Toolkit for Visual Studio Code](cloudwatchlogs.md)
+ [Working with AWS Lambda Functions](building-lambda.md)
+ [Working with Amazon S3](s3.md)
+ [Working with Amazon EventBridge](eventbridge.md)
+ [Working with AWS Step Functions](stepfunctions.md)