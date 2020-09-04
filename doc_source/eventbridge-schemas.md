# Working with Amazon EventBridge Schemas<a name="eventbridge-schemas"></a>

You can use the AWS Toolkit for Visual Studio Code \(VS Code\) to perform various operations on [Amazon EventBridge schemas](https://docs.aws.amazon.com/eventbridge/latest/userguide/eventbridge-schemas.html)\.

## Prerequisites<a name="eventbridge-schemas-prereq"></a>
+ Be sure your system meets the prerequisites specified in [Installing the Toolkit for VS Code](setup-toolkit.md#setup-prereq)\.
+ The EventBridge schema you want to work with must be available in your AWS account\. If it isn't, create or upload it\. See [Amazon EventBridge Schemas](https://docs.aws.amazon.com/eventbridge/latest/userguide/eventbridge-schemas.html) in the [Amazon EventBridge User Guide](https://docs.aws.amazon.com/eventbridge/latest/userguide/)\.
+ Open the [**AWS Explorer**](toolkit-navigation.md#aws-explorer-basic-ui) side bar\.

## View an Available Schema<a name="eventbridge-schemas-view"></a>

1. In the **AWS Explorer**, expand **Schemas**\.

1. Expand the name of the registry that contains the schema you want to view\. For example, many of the schemas that AWS supplies are in the **aws\.events** registry\.

1. To view a schema in the editor, open the context menu of the schema, and then choose **View Schema**\.  
![\[View an EventBridge schema.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/eventbridge-view.png)

## Find an Available Schema<a name="eventbridge-schemas-find"></a>

In the **AWS Explorer**, do one or more of the following:
+ Begin typing the title of the schema you want to find\. The **AWS Explorer** highlights the schema titles that contain a match\. \(A registry must be expanded for you to see the highlighted titles\.\)
+ Open the context menu for **Schemas**, and then choose **Search Schemas**\. Or expand **Schemas**, open the context menu for the registry that contains the schema you want to find, and then choose **Search Schemas in Registry**\. In the **EventBridge Schemas Search** dialog box, begin typing the title of the schema you want to find\. The dialog box displays the schema titles that contain a match\.

  To display the schema in the dialog box, select the title of the schema\.  
![\[Search for an EventBridge schema.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/eventbridge-search.png)

## Generate Code for an Available Schema<a name="eventbridge-schemas-generate-code"></a>

1. In the **AWS Explorer**, expand **Schemas**\.

1. Expand the name of the registry that contains the schema you want to generate code for\.

1. Right\-click the title of the schema, and then choose **Download code bindings**\.

1. In the resulting wizard pages, choose the following:
   + The **Version** of the schema
   + The code binding language
   + The workspace folder where you want to store the generated code on your local development machine