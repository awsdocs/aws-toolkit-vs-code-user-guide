# Deploying a Serverless Application with the AWS Toolkit for Visual Studio Code<a name="deploy-serverless-app"></a>

This example shows how to deploy the serverless application created in the previous topic to AWS using the AWS Toolkit for Visual Studio Code\.

## Prerequisites<a name="deploy-sam-prereq"></a>

\(In addition to those specified in the [Getting Started prerequisites](setup-toolkit.md#setup-prereq)\.\)
+ The Amazon S3 bucket name that you choose must be unique\.
+ The AWS credentials that you configured in [Setting Up Your AWS Credentials](setup-credentials.md) must include appropriate read/write access to the following services: Amazon S3, AWS CloudFormation, AWS Lambda, Amazon API Gateway\.

## Deploy a Serverless Application<a name="deploy-sam-proc"></a>

1. To open the **Command Palette**, choose **View**, **Command Palette**, and then enter **AWS**\.

1. Choose **AWS: Deploy SAM Application**\.  
![\[Command to deploy a serverless application.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-cmd.png)

1. Choose the `template.yaml` file to use for the deployment\.  
![\[Choose a serverless application template.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-template.png)

1. Choose the AWS Region to deploy to\.  
![\[Choose the serverless application Region.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-region.png)

1. Enter the name of an Amazon S3 bucket this deployment can use\. The bucket must be in the Region you're deploying to\.
**Warning**  
The name must be globally unique across all existing bucket names in Amazon S3\. Therefore, you should add a unique identifier to the name given in the example below \(or choose a different name\)\.  
![\[Choose the serverless application bucket.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-bucket.png)

1. Enter a name for the deployed stack, either a new stack name or an existing stack name\.  
![\[Enter a serverless application stack name.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-stack.png)

1. Verify the success of the deployment on the **OUTPUT** tab of VS Code\.  
![\[Screenshot of the output from deploying a serverless application.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-progress.png)

When the deployment is complete, you'll see your application listed in the AWS Explorer\. To learn how to invoke the Lambda function that was created as part of the application, see [Interacting with Remote Lambda Functions](remote-lambda.md)\.