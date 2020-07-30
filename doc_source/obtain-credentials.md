# Obtaining AWS access keys<a name="obtain-credentials"></a>

To access Amazon Web Services \(AWS\) with the AWS Toolkit for Visual Studio Code, you must configure the toolkit with AWS account credentials\. To do this with AWS\-supported credentials, you must first obtain appropriate AWS access keys\.

For more information about users and credentials that is out of scope for this guide, see the following resources:
+ [AWS Security Credentials](https://docs.aws.amazon.com/general/latest/gr/aws-security-credentials.html) in the *Amazon Web Services General Reference*
+ [Overview of Identity Management: Users](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction_identity-management.html) in the *IAM User Guide*

## What are AWS access keys<a name="obtain-credentials-what-are-keys"></a>

Access keys are the credentials that identify you to AWS and enable you to programmatically access AWS services and resources\. Access keys can be associated with your AWS account \(the account's "root user"\) or with users that you create with AWS Identity and Access Management \(IAM\)\.

**Warning**  
Because the root user is essentially an administrator with full access to services and resources, we recommend that you instead create an IAM user with only those permissions needed to perform the required tasks\. Then, for your credentials, you can use an access key that is associated with that user\. For details, see [Creating an IAM User in Your AWS Account](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html) in the *IAM User Guide*\.

An access key consists of an *access key ID*, which is similar to a user name, and a *secret access key*, which is similar to a password\. This access key is used to sign programmatic requests that you make to AWS\. If you don't have access keys, you can create them by using the AWS Management Console\. [We recommend that you use access keys for an IAM user instead of the keys for your account's root user](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#create-iam-users)\.

**Note**  
To create access keys, you must have permissions to perform the required IAM actions\. For more information, see [Granting IAM User Permissions to Manage Password Policy and Credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_delegate-permissions.html) in the *IAM User Guide*\.

## Get your AWS access keys<a name="obtain-credentials-get-access-keys"></a>

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. On the navigation menu, choose **Users**\.

1. Choose your IAM user name \(not the check box\) to view its details\.

1. On the **Security Credentials** tab, choose **Create access key**\.

1. To see the new access key, choose **Show**\. The credentials resemble the following:
   + Access key ID: AKIAIOSFODNN7EXAMPLE
   + Secret access key: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY

1. To download the key pair, choose **Download \.csv file**\. Store the keys in a secure location\.
**Important**  
Keep the keys confidential to protect your AWS account, and never email them\. Do not share them outside of your organization, even if an inquiry appears to come from AWS or Amazon\.com\. *No one who legitimately represents Amazon will ever ask you for your secret key*\.
You can't recover the secret key if you lose it\. Instead, for security reasons, you must create a new key pair and delete the old pair\.

After you have obtained your AWS access keys, you can use the AWS Toolkit for VS Code to store them in your shared AWS config file or your shared AWS credentials file\. See [Add your AWS access keys to your environment](setup-credentials.md#setup-credentials-set-access-keys) to learn how\.