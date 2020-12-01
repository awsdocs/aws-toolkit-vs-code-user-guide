# Running and debugging Lambda functions directly from code<a name="serverless-apps-run-debug-no-template"></a>

When testing the AWS SAM application, you can choose to run and debug just the Lambda function and exclude other resources that the AWS SAM template defines\. This approach involves using the [CodeLens](https://code.visualstudio.com/blogs/2017/02/12/code-lens-roundup) feature to identify Lambda function handlers in the source code that you can directly invoke\.

The Lambda handlers that are detected by CodeLens depend on the language and runtime that you're using for your application\.


|  Language/runtime | Criteria for Lambda functions to be identified by CodeLens indicators | 
| --- | --- | 
|  C\# \(dotnetcore2\.1 and 3\.1\)  | The function has the following features:[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/serverless-apps-run-debug-no-template.html) The [ms\-dotnettools\.csharp extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) \(or any extension that provides language symbols for C\#\) is installed and enabled\. | 
|  JavaScript \(Node\.js 10\.x and 12\.x\)  |  The function has the following features:[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/serverless-apps-run-debug-no-template.html)  | 
|  Python \(2\.7, 3\.6, 3\.7, 3\.8\)  |  The function has the following features:[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/serverless-apps-run-debug-no-template.html) The [ms\-python\.python extension](http://marketplace.visualstudio.com/items?itemName=ms-python.python) \(or any extension that provides language symbols for Python\) is installed and enabled\. | 

# To run and debug a serverless application directly from the application code

1. To view your application files in the VS Code File Explorer, choose **View**, **Explorer**\.

1. From the application folder \(for example, *my\-sample\-app*\), expand the function folder \(in this case, *hello\-world*\) and open the `app.js` file\.

1. In the CodeLens indicator that identifies an eligible Lambda function handler, choose `Add Debug Configuration`\.  
![\[Access the Add Debug Configuration option in the CodeLens indicator for a Lambda function handler.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-codelens-lambda.png)

1. In the **Command Palette**, select the runtime in which your AWS SAM application will run\.

1. In the editor for the `launch.json` file, edit or confirm values for the following configuration properties:
   + `"name"` – Enter a reader\-friendly name to appear in the **Configuration** dropdown field in the **Run** view\.
   + `"target"` – Ensure that the value is `"code"` so that a Lambda function handler is directly invoked\.
   + `"lambdaHandler"` – Enter the name of the method within your code that Lambda calls to invoke your function\. For example, for applications in JavaScript, the default is `app.lambdaHandler`\.
   + `"projectRoot"` – Enter the path to the application file that contains the Lambda function\.
   + `"runtime"` – Enter or confirm a valid runtime for the Lambda execution environment, for example, `"nodejs.12x"`\.
   + `"payload"` – Choose one of the following options to define the event payload that you want to provide to your Lambda function as input:
     + `"json"`: JSON\-formatted key\-value pairs that define the event payload\.
     + `"path"`: A path to the file that's used as the event payload\.

     In the example below, the `"json"` option defines the payload\.  
![\[Configuring the launch.json file for directly invoking Lambda functions.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/direct_invoke_config_updated_with_payload_field.png)

   For more information about these and other entries in the `launch.json` file, see [Configuration options for debugging serverless applications](serverless-apps-run-debug-config-ref.md)\.

1. If you're satisfied with the debug configuration, to start debugging, choose the green play arrow next to **RUN**\.

   When the debugging sessions starts, the **DEBUG CONSOLE** panel shows debugging output and displays any values that the Lambda function returns\. \(When debugging AWS SAM applications, **AWS Toolkit** is selected as the **Output** channel in the **Output** panel\.\)