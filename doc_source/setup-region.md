# Changing AWS Regions<a name="setup-region"></a>

When you set up your credentials, the AWS Toolkit for Visual Studio Code automatically selects and shows the default AWS Region for those credentials in the **AWS Explorer**\. This topic describes how to change the list of Regions that is shown in the **AWS Explorer**\.

## Add a Region to the AWS Explorer<a name="select-new-region"></a>

1. To open the **Command Palette**, on the menu bar, choose **View**, **Command Palette**\. Or use the following shortcut keys: 
   + Windows and Linux – Press **Ctrl\+Shift\+P**\.
   + macOS – Press **Shift\+Command\+P**\.

1. Search for **AWS** and choose **AWS: Show Region in the Explorer**\.  
![\[AWS Toolkit Command Palette showing Regions.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-show-regions.png)

1. Choose the Region that you want to add to the **AWS Explorer**\.  
![\[AWS Regions menu.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-select-region.png)
**Note**  
The list contains only those Regions that are available to add to the **AWS Explorer**\. Regions you've already added don't appear in the list\.

1. Verify that the Region now appears in the **AWS Explorer**\.  
![\[AWS Explorer Regions list.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-region-added.png)

## Hide a Region from the AWS Explorer<a name="hide-region"></a>

1. Choose the AWS icon in the **Activity bar** to open the **AWS Explorer**\.

1. Choose one of the Regions in the list, and open its context menu\.  
![\[AWS ALL Regions menu.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/aws-toolkit-region-context-menu.png)

1. Choose **Hide Region from the Explorer**\.