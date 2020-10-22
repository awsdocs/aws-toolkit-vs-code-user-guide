# Troubleshooting Systems Manager Automation documents in Toolkit for VS Code<a name="systems-manager-troubleshoot"></a>

**I saved my Automation document in VS Code, but I don’t see it in the AWS Management Console\.**  
Saving an Automation document in VS Code does not publish the Automation document to AWS\. For more information on publishing your Automation document, see [Publishing a Systems Manager Automation document](systems-manager-automation-docs.md#systems-manager-publish)\.

**Publishing my Automation document failed with a permissions error\.**  
Make sure your AWS credentials profile has the necessary permissions to publish Automation documents\. For an example permissions policy, see [IAM permissions for Systems Manager Automation documents](systems-manager-automation-docs.md#systems-manager-permissions)\.

**I published my Automation document to AWS, but I don’t see it in the AWS Management Console\.**  
Make sure that you’ve published the document to the same AWS Region you’re browsing in the AWS Management Console\.

**I’ve deleted my Automation document, but I’m still being billed for the resources it created\.**  
Deleting an Automation document doesn’t delete the resources it created or modified\. You can identify the AWS resources that you’ve created from the [AWS Billing Management Console](https://console.aws.amazon.com/billing/home), explore your charges, and choose what resources to delete from there\.