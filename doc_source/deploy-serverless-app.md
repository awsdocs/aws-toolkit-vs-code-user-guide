# Deploying serverless applications with the AWS Toolkit for Visual Studio Code<a name="deploy-serverless-app"></a>

This example shows how to deploy the serverless application that was created in the previous topic \([Creating serverless applications](create-sam.md)\) to AWS using the AWS Toolkit for Visual Studio Code\.

## Prerequisites<a name="deploy-sam-prereq"></a>
+ Be sure your system meets the prerequisites specified in [Installing the Toolkit for VS Code](setup-toolkit.md#setup-prereq)\.
+ Be sure to choose a globally unique Amazon S3 bucket name\.
+ Ensure that the credentials you configured in [Establishing credentials](establish-credentials.md) include the appropriate read/write access to the following services: Amazon S3, AWS CloudFormation, AWS Lambda, and Amazon API Gateway\.

## Deploying serverless applications<a name="deploy-sam-proc"></a>

1. To open the **Command Palette**, choose **View**, **Command Palette**, and then enter **AWS**\.

1. Choose **AWS: Deploy SAM Application**\.  
![\[Command to deploy a serverless application.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-cmd.png)

1. Choose the `template.yaml` file to use for the deployment\.  
![\[Choose a serverless application template.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-template.png)

1. Choose the AWS Region to deploy to\.  
![\[Choose the serverless application Region.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-region.png)

1. Enter the name of an Amazon S3 bucket this deployment can use\. The bucket must be in the Region you're deploying to\.
**Warning**  
The Amazon S3 bucket name must be globally unique across all existing bucket names in Amazon S3\. Therefore, you should add a unique identifier to the name given in the following example \(or choose a different name\)\.  
![\[Choose the serverless application bucket.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-bucket.png)

1. Enter a name for the deployed stack, either a new stack name or an existing stack name\.  
![\[Enter a serverless application stack name.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-stack.png)

1. Verify the success of the deployment on the **OUTPUT** tab of VS Code\.  
![\[Screenshot of the output from deploying a serverless application.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-progress.png)

   If an error occurs, a message pops up in the lower\-right that is similar to the following:  
![\[Screenshot of an error popup while deploying a serverless application.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-deploy-error.png)

   If this happens, check the text in the **OUTPUT** tab for details\. The following is an example of error details\.

   ```
   Error with child process: Unable to upload artifact HelloWorldFunction referenced by CodeUri parameter of HelloWorldFunction resource.
   S3 Bucket does not exist. Execute the command to create a new bucket
   aws s3 mb s3://pbart-my-sam-app-bucket
   An error occurred while deploying a SAM Application. Check the logs for more information by running the "View AWS Toolkit Logs" command from the Command Palette.
   ```

   In this example, the error occurred because the Amazon S3 bucket did not exist\.

When the deployment is complete, you'll see your application listed in the **AWS Explorer**\. To learn how to invoke the Lambda function that was created as part of the application, see [Interacting with Remote Lambda Functions](remote-lambda.md)\.