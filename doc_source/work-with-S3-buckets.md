# Working with Amazon S3 buckets<a name="work-with-S3-buckets"></a>

Every object you store in Amazon S3 resides in a bucket\. You can use buckets to group related objects in the same way that you use a directory to group files in a file system\.

**Topics**
+ [Creating an Amazon S3 bucket](#creating-s3-bucket)
+ [Adding a folder to an Amazon S3 bucket](#adding-folders)
+ [Deleting an Amazon S3 bucket](#deleting-s3-buckets)
+ [Configuring the display of Amazon S3 items](#configuring-items-display)

## Creating an Amazon S3 bucket<a name="creating-s3-bucket"></a>

1. In the **AWS Explorer**, right\-click the **S3** node, and then choose **Create Bucket**\. Or choose the **Create Bucket** icon across from the **S3** node\.   
![\[Creating an Amazon S3 bucket in AWS Explorer\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/s3-bucket-create.png)

1. In the **Bucket Name** field, enter a valid name for the bucket\. Press **Enter** to confirm\.

   The new bucket is displayed under the **S3** node\.
**Note**  
Because Amazon S3 allows your bucket to be used as a URL that can be accessed publicly, the bucket name that you choose must be globally unique\. If some other account has already created a bucket with the name that you chose, you must use another name\.  
You can check the **AWS Toolkit Logs** in the **Output** tab if you can't create a bucket\. For example, a `BucketAlreadyExists` error occurs if you use a bucket name already in use\. For more information, see [Bucket restrictions and limitations](https://docs.aws.amazon.com/AmazonS3/latest/dev/BucketRestrictions.html) in the *Amazon Simple Storage Service Developer Guide*\.

   After a bucket is created, you can copy its name and Amazon Resource Name \(ARN\) to the clipboard\. Right\-click the bucket entry and select the relevant option from the menu\.

## Adding a folder to an Amazon S3 bucket<a name="adding-folders"></a>

You organize a bucket's contents by grouping objects in folders\. You can also create folders within other folders\.

1. In the **AWS Explorer**, choose the **Amazon S3** node to view the list of buckets\.

1. Right\-click a bucket or a folder, and then choose **Create Folder**\. Or choose the **Create Folder** icon across from the name of the bucket or folder\.

1. Enter a **Folder Name**, and then press **Enter**\.

## Deleting an Amazon S3 bucket<a name="deleting-s3-buckets"></a>

When you delete a bucket you also delete the folders and objects that it contains\. You're asked to confirm that you want to do this before the deletion is carried out\.

**Note**  
[To delete only a folder](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/delete-folders.html), not the entire bucket, use the AWS Management Console\. 

1. In the **AWS Explorer**, choose the **S3** node to expand the list of buckets\.

1. Right\-click the bucket to delete, and then choose **Delete S3 Bucket**\.

1. Enter the bucket's name to confirm the deletion, and then press **Enter**\.
**Note**  
If the bucket contains objects, the bucket is emptied before deletion\. This can take some time if it's necessary to delete every version of thousands of objects\. A notification is displayed after the deletion is complete\.

## Configuring the display of Amazon S3 items<a name="configuring-items-display"></a>

If you're working with a large number of Amazon S3 objects or folders, you can specify how many are displayed at one time\. When the maximum number is displayed, you can choose **Load More** to display the next batch\. 

![\[Use Load More... in the AWS Explorer to view more Amazon S3 items.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/s3-load-more.png)

1. In the VS Code **Activity Bar**, choose **Extensions**\.

1. For the AWS Toolkit extension, choose the settings icon, and then choose **Extension Settings**\.

1. On the **Settings** page, scroll down to the **AWS > S3: Max Items Per Page** setting\.

1. Change the default value to the number of S3 items you want displayed before choosing to load more\.
**Note**  
The range of accepted values is between 3 and 1000\. This setting applies only to the number of objects or folders displayed at one time\. All the buckets you've created are displayed at once\. \(By default, you can create up to 100 buckets in each of your AWS accounts\.\)

1. Close the **Settings** page to confirm your changes\.

You can also update the settings in a JSON\-formatted file by choosing the **Open Settings \(JSON\)** icon in the upper right of the **Settings** page\.

![\[Choose Open Setting (JSON) to edit settings in a JSON-formatted file.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/open-json.png)