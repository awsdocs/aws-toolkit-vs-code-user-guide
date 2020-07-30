# Working with the AWS CDK Explorer<a name="cdk-explorer"></a>


****  

|  | 
| --- |
| This is prerelease documentation for a feature in preview release\. It is subject to change\. | 

The **AWS CDK Explorer** enables you to work with [AWS Cloud Development Kit \(AWS CDK\)](https://aws.amazon.com/cdk/) applications, or *apps*\. You can find detailed information about the AWS CDK in the [AWS Cloud Development Kit \(AWS CDK\) Developer Guide](https://docs.aws.amazon.com/cdk/latest/guide/)\.

AWS CDK apps are composed of building blocks known as *[constructs](https://docs.aws.amazon.com/cdk/latest/guide/constructs.html)*, which include definitions for your AWS CloudFormation stacks and the AWS resources within them\. Using the **AWS CDK Explorer**, you can visualize the [stacks](https://docs.aws.amazon.com/cdk/latest/guide/stacks.html) and [resources](https://docs.aws.amazon.com/cdk/latest/guide/resources.html) that are defined in AWS CDK constructs\. This visualization is provided in a *tree view* in an Explorer pane within the Visual Studio Code \(VS Code\) editor\. See a high\-level view of the **AWS CDK Explorer** in the [navigation](toolkit-navigation.md#cdk-explorer-basic-ui) topic\.

This section provides information about how to access and use the **AWS CDK Explorer** in the VS Code editor\. It assumes that you've already [installed and configured](setting-up.md) the Toolkit for VS Code on your system\.

**Note**  
You can disable the **AWS CDK Explorer** so that it isn't displayed in the VS Code editor\. In the **File** menu, choose **Preferences**, **Settings**\. Then enter "cdk" into the **Search** box and clear the **Enable the AWS CDK Explorer** box\.

**Topics**
+ [Working with AWS CDK applications](aws-cdk-apps.md)