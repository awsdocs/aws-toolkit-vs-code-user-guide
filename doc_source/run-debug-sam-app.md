# Running and debugging serverless applications with the AWS Toolkit for Visual Studio Code<a name="run-debug-sam-app"></a>

With AWS Toolkit for Visual Studio Code you can configure how to debug serverless applications and run them locally in your development environment\. You can debug a serverless application that's defined by a SAM \(Serverless Application Model\) template\. This template uses simple YAML syntax to describe resources such as functions, APIs, databases, and event\-source mappings that make up a serverless application\. 

For a breakdown of the AWS SAM template, see the [AWS SAM Template Anatomy](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/sam-specification-template-anatomy.html) in the *AWS Serverless Application Model Developer Guide\.* 

Alternatively, you can rapidly debug serverless applications that haven't been committed to a SAM template\.

You start to configure debug behavior by using VS Code's [CodeLens](https://code.visualstudio.com/api/language-extensions/programmatic-language-features#codelens-show-actionable-context-information-within-source-code) feature to identify an eligible Lambda function\. \(CodeLens is a Visual Studio Code feature that enables content\-aware interactions with your source code\.\) If you want to use the infrastructure defined by the SAM template, use the CodeLens indicator in the relevant YAML\-formatted file\. If you want to test the function directly without the template, use the CodeLens indicator for the lambda handler in the application file\.

**Note**  
In this example, we're debugging an application that uses JavaScript\. But you can use debugging features available in AWS Toolkit for Visual Studio Code with the following languages and runtimes:  
C\#: \.NET Core 2\.1 \(\.NET Core 3\.1 serverless applications can be run but not debugged using the Toolkit for VS Code\.\)
JavaScript: Node\.js 10\.x, 12\.x
Python: 2\.7, 3\.6, 3\.7, 3\.8
Your language choice also affects how VS Code's CodeLens detects eligible lambda handlers\. For more information, see [Running and debugging serverless functions directly from code](#run-debug-no-template)\.

## Using SAM templates to run and debug serverless applications<a name="run-debug-sam-template"></a>

For applications that are run and debugged using a SAM template, a YAML\-formatted file describes the application's behavior and the resources it uses\. If you create a serverless application with the **AWS: Create new SAM Application** option in the **Command Palette**, a file called `template.yaml` is automatically generated for your project\.

In this procedure, you'll use the sample application that was created in [Creating serverless applications with the Toolkit for VS Code](create-sam.md#create-serverless-app)\.

**Note**  
To ensure that you can access the CodeLens feature in the template file, install a VS Code extension that provides YAML language support \(for example, [YAML Language Support by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)\)\.

1. To view your application files in VS Code's File Explorer, choose **View**, **Explorer**\.

1. From the application directory \(*my\-sample\-app*, for example\), open the `template.yaml` file\.
**Note**  
If you use a template with a name that's different from `template.yaml`, the CodeLens indicator isn't automatically available in the YAML file\. This means you'll need to manually add a debug configuration\.

1. In the editor for `template.yaml`, go to the `Resources` section of the template that defines serverless resources\. In this case, the `HelloWorldFunction` resource of type `AWS::Serverless::Function`\.

   In the CodeLens indicator for this resource, click **Add Debug Configuration**\.  
![\[Using the CodeLens indicator in the template.yaml file to add a debug configuration.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/yaml_template_debug.png)

   A new editor displays the `launch.json` file that provides a debugging configuration with default attributes\.

1. Edit or confirm values for the following configuration properties:
   + `"name"`: Enter a reader\-friendly name to appear in the Debug launch configuration drop\-down\.
   + `"target"`: Ensure the value is `"template"` so that the SAM template is the entry point for the debug session\. 
   + `"templatePath"`: Enter a relative or absolute path for the `template.yaml` file\.
   + `"logicalId"`: Ensure the name matches the one specified in the Resources section of SAM template\. In this case, it's the `HelloWorldFunction` of type `AWS::Serverless::Function`\.  
![\[Configuring the launch.json file for template-based debugging.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/template_based_config_updated.png)
**Note**  
You can use VS Code's IntelliSense feature to find and autocomplete additional debug properties for your application\. For more information, see [Configuration options for debugging serverless applications](#debug-config-ref)\.

1. If you're happy with your debug configuration, save `launch.json`, and then click the green "play" button in the **RUN** view to start debugging\.

   When the debugging sessions starts, the **DEBUG CONSOLE** panel shows debugging output and displays any values returned by the Lambda function\. 
**Note**  
When debugging SAM applications, the **AWS Toolkit** is selected as the Output channel in the **Output** panel\.<a name="docker-problem"></a>
**Note**  
For Windows users, if you see a Docker mounting error during this process, you might need to refresh the credentials for your shared drives \(in Docker Settings\)\. A Docker mounting error looks like this:   

   ```
   Fetching lambci/lambda:nodejs10.x Docker container image......
                                        2019-07-12 13:36:58 Mounting C:\Users\<username>\AppData\Local\Temp\ ... as /var/task:ro,delegated inside runtime container
                                        Traceback (most recent call last):
                                         ...
                        requests.exceptions.HTTPError: 500 Server Error: Internal Server Error ...
   ```

## Running and debugging serverless functions directly from code<a name="run-debug-no-template"></a>

When testing the AWS SAM application, you can choose to run and debug just the Lambda function and exclude other resources defined by the SAM template\. This approach involves using the [CodeLens](https://code.visualstudio.com/blogs/2017/02/12/code-lens-roundup) feature to identify lambda function handlers in the source code that can be directly invoked\. 

The lambda handlers that are detected by CodeLens depend on the language and runtime you're using for your application:


|  Language/runtime  |  Criteria for adding CodeLens indicators to a Lambda function | 
| --- | --- | 
|  C\# \(dotnetcore2\.1\)  |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/run-debug-sam-app.html) | 
|  JavaScript \(Node\.js 10\.x and 12\.x\):  |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/run-debug-sam-app.html)  | 
|  Python \(node\.js 10\.x and 12\.x\):  |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/run-debug-sam-app.html)  | 

1. To view your application files in VS Code's File Explorer, choose **View**, **Explorer**\.

1. From the application directory \(*my\-sample\-app*, for example\), expand the function directory \(*hello\-world*, in this case\) and open the `app.js` file\.

1. In the CodeLens indicator that identifies an eligible lambda handler function, click `Add Debug Configuration`\.   
![\[You access the Add Debug Configuration option in the CodeLens indicator for a Lambda function handler.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/sam-codelens-lambda.png)

1. In the **Command Palette**, select the runtime in which your SAM application will run\.

1. Now, in the editor for the `launch.json` file, edit or confirm values for the following configuration properties:
   + `"name"`: Enter a reader\-friendly name to appear in the Debug launch configuration drop\-down\.
   + `"target"`: Ensure the value is `"code"` so that a lambda handler is directly invoked\. 
   + `"lambdaHandler"`: Enter the name of the method within your code that Lambda calls to invoke your function\. For example, for applications in JavaScript, `app.lambdaHandler` is the default\. 
   + `"projectRoot"`: Enter the path to the application file that contains the Lambda function\.
   + `"runtime"`: Enter or confirm a valid runtime for the Lambda execution environment\. For example, `"nodejs.12x"`\.  
![\[Configuring the launch.json file for directly invoking functions.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/direct_invoke_config.png)
**Note**  
You can use VS Code's IntelliSense feature to find and autocomplete additional debug properties for your function\. For more information, see [Configuration options for debugging serverless applications](#debug-config-ref)\.

1. If you're happy with the debug configuration, click the green play arrow beside RUN to start debugging\.

1. When the debugging sessions starts, the **DEBUG CONSOLE** panel shows debugging output and displays any values returned by the Lambda function\. 
**Note**  
When debugging SAM applications, **AWS Toolkit** is selected as the Output channel in the **Output** panel\.
**Note**  
If you see Docker mentioned in error messages, refer to this [note](#docker-problem)\.

## Configuration options for debugging serverless applications<a name="debug-config-ref"></a>

When you open the `launch.json` to edit debug configurations, you can use VS Code's [IntelliSense](https://code.visualstudio.com/docs/editor/intellisense) feature to view and autocomplete valid properties\. To trigger IntelliSense in the editor, press **Ctrl**\+**Space**\.

![\[Using VS Code's IntelliSense to find and complete a valid debug properties.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/Intellisense_autocomplete.gif)

With IntelliSense, you can easily find and define properties for invoking Lambda functions directly or with the SAM template\. You can also define properties for `"lambda"` \(how the function runs\), `"sam"` \(how the AWS SAM CLI builds the application\), and `"aws"` \(how AWS connection information is provided\)\. 


**AWS SAM: Direct Lambda handler invoke / Template\-based Lambda invoke**  

|  Property | Description | 
| --- | --- | 
|  `type`  |  Specifies which extension manages the launch configuration\. Always set to `aws-sam` to use the AWS SAM CLI to build and debug locally\.  | 
|  `name`  |  Specifies a reader\-friendly name to appear in the Debug launch configuration drop\-down\.  | 
| `request` |  Specifies the type of configuration to be performed by the designated extension \(`aws-sam`\)\. Always set to `direct-invoke` to start the Lambda function\.  | 
|  `invokeTarget`  |  Specifies the entry point for invoking the resource\. For invoking the Lambda function directly, set values for the following `invokeTarget` fields:  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/run-debug-sam-app.html) For invoking the Lambda resources with the SAM template, set values for the following `invokeTarget` fields: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/run-debug-sam-app.html)  | 


**Lambda \(`"lambda"`\) properties**  

|  Property | Description | 
| --- | --- | 
|  `environmentVariables`  |  Passes operational parameters to your function\. For example, if you're writing to an Amazon S3 bucket, instead of hard\-coding the bucket name you're writing to, configure the bucket name as an environment variable\.   | 
| `payload` |  Describes in a JSON file format the event that triggers a Lambda function\. You can create an event payload by running the following command in the **Terminal** of VS Code: `sam local generate-event apigateway aws-proxy`  | 
|  `memoryMB`  |  Specifies megabytes of memory provided for the execution of invoked Lambda function\.  | 
| `runtime` |  Specifies runtime used by the Lambda\. For more information, see [AWS Lambda runtimes](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html)\.  | 
|  `timeoutSec`  |  Sets the time allowed, in seconds, before the debug session times out\.  | 

AWS Toolkit for Visual Studio Code uses AWS SAM CLI to build and debug serverless applications locally\. You can configure the behavior of AWS SAM CLI commands using properties of the `"sam"` configuration in the `launch.json` file\.


**SAM CLI \(`"sam"`\) properties**  

| Property |  Description  |  Default value  | 
| --- | --- | --- | 
|  `buildArguments`  | Configures how the `sam build` command builds your Lambda source code\. To view build options, see [sam build](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/sam-cli-command-reference-sam-build.html) in the *AWS Serverless Application Model Developer Guide*\. |  Empty string  | 
|  `containerBuild`  |  Indicates whether to build your function inside an AWS Lambda\-like Docker container\.   |  `false`  | 
|  `dockerNetwork`  |  Specifies the name or id of an existing Docker network to Lambda Docker containers should connect to, along with the default bridge network\. If not specified, the Lambda containers will only connect to the default bridge Docker network\.   |  Empty string  | 
|  `localArguments`  |  Additional local invoke arguments\.  |  Empty string  | 
|  `skipNewImageCheck`  |  Specifies whether the command should skip pulling down the latest Docker image for Lambda runtime\.   |  `false`  | 
|  `template`  |  Customizes your SAM template by using parameters to input customer values to your template\. For more information, see [Parameters](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/parameters-section-structure.html) in the *AWS CloudFormation User Guide*\.  |  `"parameters":{}`  | 


**AWS Connection \(`"aws"`\) properties**  

| Property | Description | Default value | 
| --- | --- | --- | 
| `credentials` |  Selects a specific profile \(`profile:default`\. for example\) from your credential file to get AWS credentials\.   | The AWS credentials provided to the AWS Toolkit for Visual Studio Code by your existing [shared AWS config file or shared AWS credentials file](setup-credentials.md)\. | 
| `region` |  Sets the AWS Region of the service \(for example, us\-east\-1\)\.  | The default region associated with the active credentials profile\.  | 