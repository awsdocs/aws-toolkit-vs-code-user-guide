# Connect to AWS through the AWS Toolkit for Visual Studio Code<a name="connect"></a>

To interact with Amazon Web Services \(AWS\) through the AWS Toolkit for Visual Studio Code, you must establish a connection to AWS\.

**To connect to AWS through the Toolkit for VS Code**

1. Open VS Code\.

1. To open the **Command Palette**, on the menu bar, choose **View**, **Command Palette**, or use the following shortcut keys: 
   + Windows and Linux – Press **Ctrl\+Shift\+P**\.
   + macOS – Press **Shift\+Command\+P**\.

1. Search for **AWS** and choose **AWS: Connect to AWS**\.  
![\[AWS Toolkit Command palette, Connect to AWS\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-commandpalette.png)

1. Choose a profile from the list\.  
![\[AWS Toolkit command palette choose profile window\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-choose-profile.png)

   If you don't have a credentials profile set up, you will be prompted to set one up\. Look for a pop\-up in the lower\-right corner of the editor\. Choose **Yes** and follow the setup wizard to enter a profile name, your access key ID, and your secret access key\. For details, see [Create the Shared AWS Credentials File](setup-credentials.md#create-shared-cred-file)\.  
![\[AWS Toolkit setup profile prompt.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-cred-prompt.png)

1. Open the **AWS: Explorer** Side Bar, which we call the ***AWS Explorer***, to verify the connection\. You will see either a list of AWS Regions \(if you have made any Regions visible in the AWS Explorer\) or a message to add Regions to the AWS Explorer\.

   Before [adding Regions](setup-region.md) to the **AWS Explorer**, you see the following\.  
![\[AWS Eplorer without Regions\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-explorer-no-regions.png)

   After adding Regions to the **AWS Explorer**, you see the following\.  
![\[AWS Eplorer with regions\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-explorer-with-regions.png)

## Use Multiple AWS Accounts with the Toolkit for VS Code<a name="using-profiles"></a>

If the shared AWS credential file contains the credentials for more than one AWS account, the toolkit makes it easy for you to choose between them\. Multiple accounts can be useful, for example, to provide developers and administrators with separate resources for development and for release or publication\.

Separate sets of AWS credentials are stored as *profiles* within the shared AWS credentials file\. To choose a different set of credentials, follow the steps defined above and choose a different profile\.