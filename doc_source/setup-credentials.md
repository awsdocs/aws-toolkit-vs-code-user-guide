# Setting Up Your AWS Credentials<a name="setup-credentials"></a>

To access Amazon Web Services \(AWS\) with the AWS Toolkit for Visual Studio Code, you must configure the AWS Toolkit for Visual Studio Code with your AWS account credentials\.

**Note**  
Some features of the AWS Toolkit for Visual Studio Code, such as creating a serverless application, don't require AWS credentials\.

For details about users and credentials that are out of scope for this guide, see the following resources:
+ [AWS Security Credentials](https://docs.aws.amazon.com/general/latest/gr/aws-security-credentials.html) in the *Amazon Web Services General Reference*
+ [Overview of Identity Management: Users](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction_identity-management.html) in the *IAM User Guide*

## Get Your AWS Access Keys<a name="setup-credentials-get-access-keys"></a>

Access keys are the credentials that identify you to AWS and enable you to programmatically access AWS services and resources\. Access keys can be associated with your AWS account \(the account's "root user"\) or with users that you create with AWS Identity and Access Management \(IAM\)\. 

Because the root user is essentially an administrator with full access to services and resources, we recommend that you instead create an IAM user with only those permissions needed to perform the required tasks\. Then, for your credentials, you can use an access key that is associated with that user\. For details, see [Creating an IAM User in Your AWS Account](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html) in the *IAM User Guide*\.

An access key consists of an *access key ID*, which is analogous to a user name, and a *secret access key*, which is analogous to a password\. This access key is used to sign programmatic requests that you make to AWS\. If you don't have access keys, you can create them by using the AWS Management Console\. [We recommend that you use access keys for an IAM user instead of the keys for your account's root user](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#create-iam-users)\. 

**Note**  
To create access keys, you must have permissions to perform the required IAM actions\. For more information, see [Granting IAM User Permissions to Manage Password Policy and Credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_delegate-permissions.html) in the *IAM User Guide*\.

**To retrieve your access key ID and secret access key**

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. On the navigation menu, choose **Users**\.

1. Choose your IAM user name \(not the check box\) to view its details\.

1. Choose the **Security Credentials** tab, and then choose **Create access key**\.

1. To see the new access key, choose **Show**\. The credentials resemble the following:
   + Access key ID: AKIAIOSFODNN7EXAMPLE
   + Secret access key: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY

1. To download the key pair, choose **Download \.csv file**\. Store the keys in a secure location\.
**Important**  
Keep the keys confidential to protect your AWS account, and never email them\. Do not share them outside of your organization, even if an inquiry appears to come from AWS or Amazon\.com\. *No one who legitimately represents Amazon will ever ask you for your secret key*\.
You can't recover the secret key if you lose it\. Instead, for security reasons, you must create a new key pair and delete the old pair\.

## Add Your AWS Access Keys to the AWS Toolkit for Visual Studio Code<a name="setup-credentials-set-access-keys"></a>

The AWS Toolkit for Visual Studio Code locates and uses AWS access keys through a *shared AWS credentials file*\. This method is the same as that used by the AWS CLI and the AWS SDKs\. Access keys that you enter in the AWS Toolkit for Visual Studio Code are saved to the shared credentials file \(named `credentials`\) in the `.aws` directory within your home directory\. See [Where Are Configuration Settings Stored?](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html#cli-configure-files-where) in the *[AWS Command Line Interface User Guide](https://docs.aws.amazon.com/cli/latest/userguide/)* for more information\.

If you have already set your AWS credentials in some way, for example, by using the [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html), the AWS Toolkit for Visual Studio Code will automatically detect and make those credentials available for use\.

**Note**  
As an alternative to the procedure shown below, the AWS CLI command `[aws configure](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html)` can be used to add AWS credentials to your environment\. This command can also be used to set the default region, which is needed for certain operations such as creating a serverless application\.

**To add your access keys to the AWS Toolkit for Visual Studio Code**

1. Open VS Code\.

1. To open the **Command Palette**, on the menu bar, choose **View**, **Command Palette**, or use the following shortcut keys: 
   + Windows and Linux – Press **Ctrl\+Shift\+P**\.
   + macOS – Press **Shift\+Command\+P**\.

1. Search for **AWS** and choose **AWS: Connect to AWS**\.  
![\[AWS Toolkit Command palette\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-commandpalette.png)

1. Choose a profile from the list\.  
![\[AWS Toolkit command palette choose profile window\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-choose-profile.png)

   If you don't have any credentials set up, you will be prompted to set one up\. Choose **Yes** and follow the setup wizard to enter a profile name, your access key ID and your secret access key\.  
![\[AWS Toolkit setup profile prompt.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-cred-prompt.png)

To use a new set of credentials, you can add a new profile through the AWS Toolkit for Visual Studio Code by using the **AWS: Create Credentials Profile** command\.

**To add a new profile to your AWS credentials file**

1. Open VS Code\.

1. To open the **Command Palette**, on the menu bar, choose **View**, **Command Palette**, or use the following shortcut keys\. 
   + Windows and Linux – Press **Ctrl\+Shift\+P**\.
   + macOS – Press **Shift\+Command\+P**\.

1. Search for **AWS** and choose **AWS: Create Credentials Profile**\.  
![\[AWS Toolkit command palette.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-cmd-create-cred.png)

1. When the AWS credentials and configuration files open in the VS Code editor, add additional profiles\. 

Once your credentials are added and saved to the file, you can start using the AWS Toolkit for Visual Studio Code with AWS\. Choose the AWS icon in the **Activity bar** to see all the AWS Lambda applications and functions that are defined in your account\. 

![\[AWS Explorer with credentials defined.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-explorer-with-cred.png)

## Use Multiple AWS Accounts with the AWS Toolkit for Visual Studio Code<a name="using-profiles"></a>

If the credential file contains more than one AWS account, the toolkit makes it easy for you to choose between them\. Multiple accounts can be useful, for example, to provide developers and administrators with separate resources for development and for release or publication\.

Separate sets of AWS credentials are stored as *profiles* within the shared AWS credentials file\. To choose a different set of credentials to use, follow the steps described in [Add Your AWS Access Keys to the AWS Toolkit for Visual Studio Code](#setup-credentials-set-access-keys) and choose a different profile\. 