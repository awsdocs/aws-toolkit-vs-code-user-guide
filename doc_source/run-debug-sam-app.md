# Running and debugging serverless applications with the AWS Toolkit for Visual Studio Code<a name="run-debug-sam-app"></a>

You can use the AWS Toolkit for Visual Studio Code to configure how to debug serverless applications and run them locally in your development environment\. You can debug a serverless application that's defined by an AWS Serverless Application Model \(AWS SAM\) template\. This template uses simple YAML syntax to describe resources such as functions, APIs, databases, and event\-source mappings that make up a serverless application\. 

For a closer look at the AWS SAM template, see the [AWS SAM template anatomy](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/sam-specification-template-anatomy.html) in the *AWS Serverless Application Model Developer Guide\.* 

Alternatively, you can rapidly debug serverless applications that haven't been committed to a SAM template\.

You start to configure debug behavior by using the Visual Studio Code \(VS Code\) [CodeLens](https://code.visualstudio.com/api/language-extensions/programmatic-language-features#codelens-show-actionable-context-information-within-source-code) feature to identify an eligible AWS Lambda function\. \(CodeLens enables content\-aware interactions with your source code\.\) To use the infrastructure defined by the SAM template, use the CodeLens indicator in the relevant YAML\-formatted file\. To test the function directly without the template, use the CodeLens indicator for the Lambda handler in the application file\.

**Note**  
In this example, we're debugging an application that uses JavaScript\. But you can use debugging features available in the AWS Toolkit for Visual Studio Code with the following languages and runtimes:  
C\# – \.NET Core 2\.1 \(\.NET Core 3\.1 serverless applications can be run but not debugged by using the Toolkit for VS Code\.\)
JavaScript – Node\.js 10\.*x*, 12\.*x*
Python – 2\.7, 3\.6, 3\.7, 3\.8
Your language choice also affects how VS Code's CodeLens detects eligible Lambda handlers\. For more information, see [Running and debugging serverless functions directly from code](#run-debug-no-template)\.

## Using SAM templates to run and debug serverless applications<a name="run-debug-sam-template"></a>

For applications that are run and debugged using a SAM template, a YAML\-formatted file describes the application's behavior and the resources it uses\. If you create a serverless application with the **AWS: Create new SAM Application** option in the **Command Palette**, a file named `template.yaml` is automatically generated for your project\.

In this procedure, you'll use the example application that was created in [Creating serverless applications with the Toolkit for VS Code](create-sam.md#create-serverless-app)\.

**Note**  
To ensure that you can access the CodeLens feature in the template file, install a VS Code extension that provides YAML language support \(for example, [YAML language support by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)\)\.

## To use a SAM template to run and debug a serverless application

1. To view your application files in VS Code's File Explorer, choose **View**, **Explorer**\.

1. From the application folder \(for example, *my\-sample\-app*\), open the `template.yaml` file\.
**Note**  
If you use a template with a name that's different from `template.yaml`, the CodeLens indicator isn't automatically available in the YAML file\. This means you need to manually add a debug configuration\.

1. In the editor for `template.yaml`, go to the `Resources` section of the template that defines serverless resources\. In this case, this is the `HelloWorldFunction` resource of type `AWS::Serverless::Function`\.

   In the CodeLens indicator for this resource, choose **Add Debug Configuration**\.  
![\[Using the CodeLens indicator in the template.yaml file to add a debug configuration.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/yaml_template_debug.png)

   A new editor displays the `launch.json` file that provides a debugging configuration with default attributes\.

1. Edit or confirm values for the following configuration properties:
   + `"name"` – Enter a reader\-friendly name to appear in the **Configuration** drop\-down field in the **Run** view\.
   + `"target"` – Ensure the value is `"template"` so that the SAM template is the entry point for the debug session\. 
   + `"templatePath"` – Enter a relative or absolute path for the `template.yaml` file\.
   + `"logicalId"` – Ensure the name matches the one specified in the **Resources** section of SAM template\. In this case, it's the `HelloWorldFunction` of type `AWS::Serverless::Function`\.  
![\[Configuring the launch.json file for template-based debugging.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/template_based_config_updated.png)
**Note**  
You can use VS Code's IntelliSense feature to find and automatically complete additional debug properties for your application\. For more information, see [Configuration options for debugging serverless applications](#debug-config-ref)\.

1. If you're satisfied with your debug configuration, save `launch.json`\. Then choose the green "play" button in the **RUN** view to start debugging\.

   When the debugging sessions starts, the **DEBUG CONSOLE** panel shows debugging output and displays any values returned by the Lambda function\. \(When debugging SAM applications, the **AWS Toolkit** is selected as the **Output** channel in the **Output** panel\.\)<a name="docker-problem"></a>
**Note**  
For Windows users, if you see a Docker mounting error during this process, you might need to refresh the credentials for your shared drives \(in **Docker Settings**\)\. A Docker mounting error looks like the following\.   

   ```
   Fetching lambci/lambda:nodejs10.x Docker container image......
                                        2019-07-12 13:36:58 Mounting C:\Users\<username>\AppData\Local\Temp\ ... as /var/task:ro,delegated inside runtime container
                                        Traceback (most recent call last):
                                         ...
                        requests.exceptions.HTTPError: 500 Server Error: Internal Server Error ...
   ```

## Running and debugging serverless functions directly from code<a name="run-debug-no-template"></a>

When testing the AWS SAM application, you can choose to run and debug just the Lambda function and exclude other resources defined by the SAM template\. This approach involves using the [CodeLens](https://code.visualstudio.com/blogs/2017/02/12/code-lens-roundup) feature to identify Lambda function handlers in the source code that can be directly invoked\. 

The Lambda handlers that are detected by CodeLens depend on the language and runtime you're using for your application\.


|  Language/runtime  | Criteria for Lambda functions to be identified by CodeLens indicators | 
| --- | --- | 
|  C\# \(dotnetcore2\.1\)  | The function has the following features:[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/run-debug-sam-app.html) | 
|  JavaScript \(Node\.js 10\.x and 12\.x\)  |  The function has the following features: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/run-debug-sam-app.html)  | 
|  Python \(node\.js 10\.x and 12\.x\)  |  The function has the following features: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/run-debug-sam-app.html)  | 

## To run and debug a serverless application directly from the application code

1. To view your application files in the VS Code File Explorer, choose **View**, **Explorer**\.

1. From the application folder \(*my\-sample\-app*, for example\), expand the function folder \(*hello\-world*, in this case\) and open the `app.js` file\.

1. In the CodeLens indicator that identifies an eligible Lambda handler function, choose `Add Debug Configuration`\.   
![\[Access the Add Debug Configuration option in the CodeLens indicator for a Lambda function handler.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-codelens-lambda.png)

1. In the **Command Palette**, select the runtime in which your SAM application will run\.

1. In the editor for the `launch.json` file, edit or confirm values for the following configuration properties:
   + `"name"` – Enter a reader\-friendly name to appear in the **Configuration** drop\-down field in the **Run** view\. 
   + `"target"` – Ensure the value is `"code"` so that a Lambda handler is directly invoked\. 
   + `"lambdaHandler"` – Enter the name of the method within your code that Lambda calls to invoke your function\. For example, for applications in JavaScript, the default is `app.lambdaHandler`\. 
   + `"projectRoot"` – Enter the path to the application file that contains the Lambda function\.
   + `"runtime"` – Enter or confirm a valid runtime for the Lambda execution environment, for example, `"nodejs.12x"`\.
   + `"payload"` – Choose one the following options to define the event payload you want to provide to your Lambda function as input:
     + `"json"`: JSON\-formatted key\-value pairs that define the event payload\.
     + `"path"`: A path to the file that's used as the event payload\.

     In the example below, the `"json"` option defines the payload\.  
![\[Configuring the launch.json file for directly invoking functions.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/direct_invoke_config_updated_with_payload_field.png)
**Note**  
You can use the VS Code IntelliSense feature to find and automatically complete additional debug properties for your function\. For more information, see [Configuration options for debugging serverless applications](#debug-config-ref)\.

1. If you're satisfied with the debug configuration, choose the green play arrow next to **RUN** to start debugging\.

   When the debugging sessions starts, the **DEBUG CONSOLE** panel shows debugging output and displays any values returned by the Lambda function\. \(When debugging SAM applications, **AWS Toolkit** is selected as the **Output** channel in the **Output** panel\.\)
**Note**  
If you see Docker mentioned in error messages, see this [note](#docker-problem)\.

## Configuration options for debugging serverless applications<a name="debug-config-ref"></a>

When you open the `launch.json` file to edit debug configurations, you can use the VS Code [IntelliSense](https://code.visualstudio.com/docs/editor/intellisense) feature to view and automatically complete valid properties\. To trigger IntelliSense in the editor, press **Ctrl**\+**Spacebar**\.

![\[Using VS Code's IntelliSense to find and complete valid debug properties.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/Intellisense_autocomplete.gif)

With IntelliSense, you can easily find and define properties for invoking Lambda functions directly or with the SAM template\. You can also define properties for `"lambda"` \(how the function runs\), `"sam"` \(how the AWS SAM CLI builds the application\), and `"aws"` \(how AWS connection information is provided\)\. 


**AWS SAM: Direct Lambda handler invoke / Template\-based Lambda invoke**  

|  Property | Description | 
| --- | --- | 
|  `type`  |  Specifies which extension manages the launch configuration\. Always set to `aws-sam` to use the AWS SAM CLI to build and debug locally\.  | 
|  `name`  |  Specifies a reader\-friendly name to appear in the **Debug launch configuration** list\.  | 
| `request` |  Specifies the type of configuration to be performed by the designated extension \(`aws-sam`\)\. Always set to `direct-invoke` to start the Lambda function\.  | 
|  `invokeTarget`  |  Specifies the entry point for invoking the resource\. For invoking the Lambda function directly, set values for the following `invokeTarget` fields:  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/run-debug-sam-app.html) For invoking the Lambda resources with the SAM template, set values for the following `invokeTarget` fields: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/run-debug-sam-app.html)  | 


**Lambda \(`"lambda"`\) properties**  

|  Property | Description | 
| --- | --- | 
|  `environmentVariables`  |  Passes operational parameters to your function\. For example, if you're writing to an Amazon S3 bucket, instead of hard\-coding the bucket name you're writing to, configure the bucket name as an environment variable\.  When specifying environment variables for a serverless application, you must add configurations to both the SAM template \(`template.yaml`\) and the `launch.json` file\.  Example of formatting for an environment variable in the SAM template: <pre>Resources:<br /> HelloWorldFunction:<br /> Type: AWS::Serverless::Function<br /> Properties:<br />   CodeUri: hello-world/<br />   Handler: app.lambdaHandlerN10<br />   Runtime: nodejs10.x<br />   Environment:<br />     Variables:<br />       SAMPLE1: Default Sample 1 Value</pre> Example of formatting for an environment variable in the `launch.json` file: <pre>"environmentVariables": {<br />    "SAMPLE1": "My sample 1 value"<br /> }</pre>   | 
| `payload` |  Provides two options for the event payload you provide to your Lambda function as input\. [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/run-debug-sam-app.html)  | 
|  `memoryMB`  |  Specifies megabytes of memory provided for running an invoked Lambda function\.  | 
| `runtime` |  Specifies the runtime used by the Lambda function\. For more information, see [AWS Lambda runtimes](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html)\.  | 
|  `timeoutSec`  |  Sets the time allowed, in seconds, before the debug session times out\.  | 

The AWS Toolkit for Visual Studio Code uses the AWS SAM CLI to build and debug serverless applications locally\. You can configure the behavior of AWS SAM CLI commands using properties of the `"sam"` configuration in the `launch.json` file\.


**AWS SAM CLI \(`"sam"`\) properties**  

| Property |  Description  |  Default value  | 
| --- | --- | --- | 
|  `buildArguments`  | Configures how the `sam build` command builds your Lambda source code\. To view build options, see [sam build](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/sam-cli-command-reference-sam-build.html) in the *AWS Serverless Application Model Developer Guide*\. |  Empty string  | 
|  `containerBuild`  |  Indicates whether to build your function inside an AWS Lambda\-like Docker container\.   |  `false`  | 
|  `dockerNetwork`  |  Specifies the name or ID of an existing Docker network that the Lambda Docker containers should connect to, along with the default bridge network\. If not specified, the Lambda containers only connect to the default bridge Docker network\.   |  Empty string  | 
|  `localArguments`  |  Additional local invoke arguments\.  |  Empty string  | 
|  `skipNewImageCheck`  |  Specifies whether the command should skip pulling down the latest Docker image for Lambda runtime\.   |  `false`  | 
|  `template`  |  Customizes your SAM template by using parameters to input customer values to it\. For more information, see [Parameters](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/parameters-section-structure.html) in the *AWS CloudFormation User Guide*\.  |  `"parameters":{}`  | 


**AWS connection \(`"aws"`\) properties**  

| Property | Description | Default value | 
| --- | --- | --- | 
| `credentials` |  Selects a specific profile \(for example, `profile:default`\) from your credential file to get AWS credentials\.   | The AWS credentials provided to the AWS Toolkit for Visual Studio Code by your existing [shared AWS config file or shared AWS credentials file](setup-credentials.md)\. | 
| `region` |  Sets the AWS Region of the service \(for example, us\-east\-1\)\.  | The default AWS Region associated with the active credentials profile\.  | 