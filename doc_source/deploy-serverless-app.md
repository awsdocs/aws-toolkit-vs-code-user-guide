# Deploying a Serverless Application with the AWS Toolkit for Visual Studio Code<a name="deploy-serverless-app"></a>

 This example shows how to deploy a serverless application to AWS using the AWS Toolkit for Visual Studio Code\. 

**To deploy a serverless application with the AWS Toolkit for Visual Studio Code**

1. Open the **Command Palette** and enter **AWS**\.

1. Choose **AWS: Deploy SAM Application**\.  
![\[Command to deploy a serverless application.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-cmd.png)

1. Choose the `template.yaml` file to use for the deployment\.  
![\[Choose a serverless application template.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-template.png)

1. Choose the Region to deploy to\.  
![\[Choose the serverless application Region.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-region.png)

1. Enter the name of an Amazon S3 bucket this deployment can use\. The bucket must be in the Region you're deploying to\.  
![\[Choose the serverless application bucket.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-bucket.png)

1. Enter a name for the deployed stack, either a new stack name or an existing stack name\.  
![\[Enter a serverless application stack name.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-stack.png)

1. Verify the success of the the deployment on the **OUTPUT** tab of VS Code\.  
![\[Screenshot of the output from deploying a serverless application.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-progress.png)

When the deployment is complete, you'll see your application listed in the AWS Explorer\. See the [Interacting with Remote Lambda Functions](remote-lambda.md) to learn how to invoke the Lambda function that was created as part of the application\.