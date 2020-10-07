# Working with Systems Manager Automation documents<a name="systems-manager-automation-docs"></a>

AWS Systems Manager gives you visibility and control of your infrastructure on AWS\. Systems Manager provides a unified user interface so you can view operational data from multiple AWS services and automate operational tasks across your AWS resources\.

A [Systems Manager document](https://docs.aws.amazon.com/systems-manager/latest/userguide/sysman-systems-manager-docs.html) defines the actions that Systems Manager performs on your managed instances\. An Automation document is a type of Systems Manager document that you use to perform common maintenance and deployment tasks such as creating or updating an Amazon Machine Image \(AMI\)\. This topic outlines how to create, edit, publish, and delete Automation documents with AWS Toolkit for Visual Studio Code\.

**Topics**
+ [Assumptions and prerequisites](#systems-manager-assumptions)
+ [IAM permissions for Systems Manager Automation documents](#systems-manager-permissions)
+ [Creating a new Systems Manager Automation document](#systems-manager-create)
+ [Opening an existing Systems Manager Automation document](#systems-manager-open)
+ [Editing a Systems Manager Automation document](#systems-manager-edit)
+ [Publishing a Systems Manager Automation document](#systems-manager-publish)
+ [Deleting a Systems Manager Automation document](#systems-manager-delete)
+ [Executing a Systems Manager Automation document](#systems-manager-run)
+ [Troubleshooting Systems Manager Automation documents in Toolkit for VS Code](systems-manager-troubleshoot.md)

## Assumptions and prerequisites<a name="systems-manager-assumptions"></a>

Before you begin, make sure:
+ You have installed Visual Studio Code and the latest version of the AWS Toolkit for Visual Studio Code\. For more information, see [Installing the AWS Toolkit for Visual Studio Code](setup-toolkit.md)\.
+ You’re familiar with Systems Manager\. For more information, see the [https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html](https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html)\.
+ You’re familiar with Systems Manager Automation use cases\. For more information, see [AWS Systems Manager Automation](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-automation.html) in the *AWS Systems Manager User Guide*\.

## IAM permissions for Systems Manager Automation documents<a name="systems-manager-permissions"></a>

In the Toolkit for VS Code you must have a credentials profile that contains the AWS Identity and Access Management \(IAM\) permissions necessary to create, edit, publish, and delete Systems Manager Automation documents\. The following policy document defines the necessary IAM permissions that can be used in a principal policy:

```
{
  "Version": "2012-10-17",
  "Statement" : [
    {
      "Effect" : "Allow",
      "Action" : [
        "systems-manager:ListDocuments",
        "systems-manager:ListDocumentVersions",
        "systems-manager:DescribeDocument",
        "systems-manager:GetDocument",
        "systems-manager:CreateDocument",
        "systems-manager:UpdateDocument",
        "systems-manager:UpdateDocumentDefaultVersion",
        "systems-manager:DeleteDocument"
      ],
      "Resource" : "*"
    }
  ]
}
```

For information on how to update an IAM policy, see [Creating IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html) in the *IAM User Guide*\. For information on how to set up your credentials profile, see [Setting up your AWS credentials](setup-credentials.md)\. 

## Creating a new Systems Manager Automation document<a name="systems-manager-create"></a>

You can create a new Automation document in `JSON` or `YAML` using Visual Studio Code\. When you create a new Automation document, it will be presented in an untitled file\. You can name your file and save it in VS Code, however the name of the file isn't visible to AWS\.

**To create a new Automation document**

1. Open VS Code\.

1. On the **View** menu, choose **Command Palette** to open the Command Palette\.

1. In the Command Palette, enter **AWS: Create a new Systems Manager Document Locally**\.

1. Choose one of the starter templates for a Hello World example\.

1. Choose either `JSON` or `YAML`\.

   A new Automation document is created\.

**Note**  
Your new Automation document in VS Code doesn't automatically appear in AWS\. You must publish it to AWS before you can execute it\. 

## Opening an existing Systems Manager Automation document<a name="systems-manager-open"></a>

You use the AWS Explorer to find existing Systems Manager Automation documents\. When you open an existing Automation document, it appears as an untitled file in VS Code\.

**To open your Automation document**

1. Open VS Code\.

1. From the left\-hand navigation, choose **AWS** to open the AWS Explorer\.

1. In the AWS Explorer, for **Systems Manager**, choose the download icon on the document that you want to open and then choose the document version\. The file will open in the format for that version\. Otherwise choose either **Download as JSON **or **Download as YAML**\.

**Note**  
Locally saving an Automation document as a file in VS Code doesn't make it appear in AWS\. It needs to be published to AWS before executing\.

## Editing a Systems Manager Automation document<a name="systems-manager-edit"></a>

If you own any Automation documents, they appear in the **Owned by Me** category of Systems Manager documents in the AWS Explorer\. You can own Automation documents that already exist in AWS, and you can own new or updated documents that you previously published to AWS from VS Code\.

When you open an Automation document for editing in VS Code, you can do more with it than you can in the AWS Management Console\. For example:
+ There is schema validation on both `JSON` and `YAML` formats\.
+ There are snippets available in the document editor for you to create any of the automation step types\.
+ There is auto\-complete support on various options in `JSON` and `YAML`\.

### Working with versions<a name="systems-manager-edit-default-version"></a>

Systems Manager Automation documents use versions for change management\. You can choose the default version for an Automation document in VS Code\. 

**To set a default version**
+ In the AWS Explorer, navigate to the document that you want to set the default version on, open the context \(right\-click\) menu for the document, and choose **Set default version**\.
**Note**  
If the chosen document only has one version, you won't be able to change the default\.

## Publishing a Systems Manager Automation document<a name="systems-manager-publish"></a>

After you edit your Automation document in VS Code, you can publish it to AWS\.

**To publish your Automation document**

1. Open the Automation document that you want to publish using the procedure outlined in [Opening an existing Systems Manager Automation document](#systems-manager-open)\.

1. Make the changes that you want to be published\. For more information, see [Editing a Systems Manager Automation document](#systems-manager-edit)\.

1. In the upper right of the open file, choose the upload icon\.

1. In the publishing workflow dialog box, choose the AWS Region that you want to publish the Automation document to\.

1. If you're publishing a new document, choose **Quick Create**\. Otherwise, choose **Quick Update** to update an existing Automation document in that AWS Region\.

1. Enter the name for this Automation document\.

When you publish an update to an existing Automation document to AWS, a new version is added to the document\.

## Deleting a Systems Manager Automation document<a name="systems-manager-delete"></a>

You can delete Automation documents in VS Code\. Deleting an Automation document deletes the document and all versions of the document\. 

**Important**  
Deleting is a destructive action that can't be undone\.
Deleting an Automation document that has already been executed doesn't delete the AWS resources that were created or modified when it was executed\.

**To delete your Automation document**

1. Open VS Code\.

1. From the left\-hand navigation, choose **AWS** to open the AWS Explorer\.

1. In the AWS Explorer, for **Systems Manager**, open the context \(right\-click\) menu for the document you want to delete, and choose **Delete document**\.

## Executing a Systems Manager Automation document<a name="systems-manager-run"></a>

Once your Automation document is published to AWS, you can execute it to perform tasks on your behalf in your AWS account\. To execute your Automation document, you use the AWS Management Console, the Systems Manager APIs, the AWS CLI, or the AWS Tools for PowerShell\. For instructions on how to execute an Automation document, see [Running a simple automation](https://docs.aws.amazon.com/systems-manager/latest/userguide/automation-working-executing.html) in the *AWS Systems Manager User Guide*\.

Alternatively, if you want to use one of the AWS SDKs with the Systems Manager APIs to execute your Automation document, see the [AWS SDK references](https://aws.amazon.com/getting-started/tools-sdks/)\.

**Note**  
Executing an Automation document can create new resources in AWS and can incur billing costs\. We strongly recommend that you understand what your Automation document will create in your account before you execute it\.