# Working with CloudWatch log events in log streams by using the AWS Toolkit for Visual Studio Code<a name="working-CloudWatch-log-events"></a>

After you've opened the **Log Steam** editor, you can access the log events in each stream\. Log events are records of activity recorded by the application or resource being monitored\.

**Topics**
+ [Viewing and copying log stream information](#viewing-log-events)
+ [Save the contents of the log stream editor to a local file](#saving-CW-logs)

## Viewing and copying log stream information<a name="viewing-log-events"></a>

When you open a log stream, the **Log Stream** editor displays that stream's sequence of log events\.

1. To find a log stream to view, open the **Log Stream** editor \(see [Viewing CloudWatch log groups and log streams](viewing-CloudWatch-logs.md)\)\.

   Each line listing an event is timestamped to show when it was logged\. 

1. You can view and copy information about the stream's events using the following options:
   + View events by time: Display the latest and older log events by choosing **Load newer events** or **Load older events**\. 
**Note**  
The **Log Stream** editor initially loads a batch of the most recent 10,000 lines of log events or 1 MB of log data \(whichever is smaller\)\. If you choose **Load newer events**, the editor displays events that were logged after the last batch was loaded\. If you choose **Load older events**, the editor displays a batch of events that occurred before those currently displayed\. 
   + Copy log events: Select the events to copy, then right\-click and select **Copy** from the menu\.
   + Copy the log stream's name: Right\-click the tab of **Log Stream** editor and choose **Copy Log Stream Name**\.
**Note**  
You can also use the **Command Palette** to run **AWS: Copy Log Stream Name**\.

## Save the contents of the log stream editor to a local file<a name="saving-CW-logs"></a>

You can download the contents of the CloudWatch log stream editor to a `log` file on your local machine\.

**Note**  
With this option, you save to file only the log events that are currently displayed in the log stream editor\. For example, if the total size of a log stream is 5MB and only 2MB is loaded in the editor, your saved file will also contain only 2MB of log data\. To display more data to be saved, choose **Load newer events** or **Load older events** in the editor\. 

1. To find a log stream to copy, open the **Log Streams** editor \(see [Viewing CloudWatch log groups and log streams](viewing-CloudWatch-logs.md)\)\.

1. Choose the **Save** icon beside the tab displaying the log stream's name\.
**Note**  
You can also use the **Command Palette** to run **AWS: Save Current Log Stream Content**\.

1. Use the dialog box to select or create a download folder for the log file, and click **Save**\.