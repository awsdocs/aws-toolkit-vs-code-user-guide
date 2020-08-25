# Viewing CloudWatch log groups and log streams by using the AWS Toolkit for Visual Studio Code<a name="viewing-CloudWatch-logs"></a>

A *log stream* is a sequence of log events that share the same source\. Each separate source of logs into CloudWatch Logs makes up a separate log stream\.

 A *log group* is a group of log streams that share the same retention, monitoring, and access control settings\. You can define log groups and specify which streams to put into each group\. There is no limit on the number of log streams that can belong to one log group\. 

For more information, see [Working with Log Groups and Log Streams ](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Working-with-log-groups-and-streams.html) in the *Amazon CloudWatch User Guide*\.

**Topics**
+ [Viewing log groups and log streams with the **CloudWatch Logs** node](#viewing-log-groups)

## Viewing log groups and log streams with the **CloudWatch Logs** node<a name="viewing-log-groups"></a>

1. In VS Code, choose **View**, **Explorer** to open AWS Explorer\.

1. Click the **CloudWatch Logs** node to expand the list of log groups\.

   The log groups for the current AWS Region are displayed under the **CloudWatch Logs** node\.

1. To view the log streams in a log group, right\-click the name of the log group, and then choose **View Log Stream**\.  
![\[Viewing log streams in a CloudWatch log group in AWS Explorer\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/cwl-log-streams.png)

1. From the **Command Palette**, select a log stream from the group to view\.
**Note**  
The **Command Palette** displays a timestamp for the last event in each stream\.

   The [**Log Stream** editor](working-CloudWatch-log-events.md) launches to display the stream's log events\. 