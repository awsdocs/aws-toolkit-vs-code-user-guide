# Configuration options for debugging serverless applications<a name="serverless-apps-run-debug-config-ref"></a>

When you open the `launch.json` file to edit debug configurations, you can use the VS Code [IntelliSense](https://code.visualstudio.com/docs/editor/intellisense) feature to view and automatically complete valid properties\. To trigger IntelliSense in the editor, press **Ctrl**\+**Spacebar**\.

![\[Using VS Code's IntelliSense to find and complete valid debug properties.\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/images/Intellisense_autocomplete.gif)

IntelliSense enables you to find and define properties for invoking Lambda functions directly or with the AWS SAM template\. You can also define properties for `"lambda"` \(how the function runs\), `"sam"` \(how the AWS SAM CLI builds the application\), and `"aws"` \(how AWS connection information is provided\)\.


**AWS SAM: Direct Lambda handler invoke / Template\-based Lambda invoke**  

|  Property | Description | 
| --- | --- | 
|  `type`  |  Specifies which extension manages the launch configuration\. Always set to `aws-sam` to use the AWS SAM CLI to build and debug locally\.  | 
|  `name`  |  Specifies a reader\-friendly name to appear in the **Debug launch configuration** list\.  | 
| `request` |  Specifies the type of configuration to be performed by the designated extension \(`aws-sam`\)\. Always set to `direct-invoke` to start the Lambda function\.  | 
|  `invokeTarget`  |  Specifies the entry point for invoking the resource\. For invoking the Lambda function directly, set values for the following `invokeTarget` fields: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/serverless-apps-run-debug-config-ref.html) For invoking the Lambda resources with the AWS SAM template, set values for the following `invokeTarget` fields: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/serverless-apps-run-debug-config-ref.html)  | 


**Lambda \(`"lambda"`\) properties**  

|  Property | Description | 
| --- | --- | 
|  `environmentVariables`  |  Passes operational parameters to your Lambda function\. For example, if you're writing to an Amazon S3 bucket, instead of hard\-coding the bucket name that you're writing to, configure the bucket name as an environment variable\.  When specifying environment variables for a serverless application, you must add configurations to both the AWS SAM template \(`template.yaml`\) and the `launch.json` file\. Example of formatting for an environment variable in the AWS SAM template: <pre>Resources:<br /> HelloWorldFunction:<br /> Type: AWS::Serverless::Function<br /> Properties:<br />   CodeUri: hello-world/<br />   Handler: app.lambdaHandlerN10<br />   Runtime: nodejs10.x<br />   Environment:<br />     Variables:<br />       SAMPLE1: Default Sample 1 Value</pre> Example of formatting for an environment variable in the `launch.json` file: <pre>"environmentVariables": {<br />    "SAMPLE1": "My sample 1 value"<br /> }</pre>   | 
| `payload` |  Provides two options for the event payload that you provide to your Lambda function as input\. [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/serverless-apps-run-debug-config-ref.html)  | 
|  `memoryMB`  |  Specifies megabytes \(MB\) of memory provided for running an invoked Lambda function\.  | 
| `runtime` |  Specifies the runtime that the Lambda function uses\. For more information, see [AWS Lambda runtimes](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html)\.  | 
|  `timeoutSec`  |  Sets the time allowed, in seconds, before the debug session times out\.  | 
|  `pathMappings`  |  Specifies where local code is in relation to where it runs in the container\. By default, the Toolkit for VS Code sets `localRoot` to the Lambda function's code root in the local workspace, and `remoteRoot` to `/var/task`, which is the default working directory for code running in Lambda\. If the working directory is changed in the Dockerfile or with the `WorkingDirectory` parameter in the AWS CloudFormation template file, at least one `pathMapping` entry must be specified so that the debugger can successfully map locally set breakpoints to the code running in the Lambda container\. Example of formatting for `pathMappings` in the `launch.json` file: <pre>"pathMappings": [<br />    {<br />        "localRoot": "${workspaceFolder}/sam-app/HelloWorldFunction",<br />        "remoteRoot": "/var/task"<br />    }<br />]</pre> Caveats: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/serverless-apps-run-debug-config-ref.html)  | 

The Toolkit for VS Code uses the AWS SAM CLI to build and debug serverless applications locally\. You can configure the behavior of AWS SAM CLI commands using properties of the `"sam"` configuration in the `launch.json` file\.


**AWS SAM CLI \(`"sam"`\) properties**  

| Property |  Description |  Default value | 
| --- | --- | --- | 
|  `buildArguments`  | Configures how the `sam build` command builds your Lambda source code\. To view build options, see [sam build](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/sam-cli-command-reference-sam-build.html) in the *AWS Serverless Application Model Developer Guide*\. |  Empty string  | 
|  `containerBuild`  |  Indicates whether to build your function inside a Lambda\-like Docker container\.  |  `false`  | 
|  `dockerNetwork`  |  Specifies the name or ID of an existing Docker network that the Lambda Docker containers should connect to, along with the default bridge network\. If not specified, the Lambda containers connect only to the default bridge Docker network\.  |  Empty string  | 
|  `localArguments`  |  Specifies additional local invoke arguments\.  |  Empty string  | 
|  `skipNewImageCheck`  |  Specifies whether the command should skip pulling down the latest Docker image for Lambda runtime\.  |  `false`  | 
|  `template`  |  Customizes your AWS SAM template using parameters to input customer values\. For more information, see [Parameters](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/parameters-section-structure.html) in the *AWS CloudFormation User Guide*\.  |  `"parameters":{}`  | 


**AWS connection \(`"aws"`\) properties**  

| Property | Description | Default value | 
| --- | --- | --- | 
| `credentials` |  Selects a specific profile \(for example, `profile:default`\) from your credential file to get AWS credentials\.  | The AWS credentials that your existing [shared AWS config file or shared AWS credentials file](setup-credentials.md) provide to the Toolkit for VS Code\. | 
| `region` |  Sets the AWS Region of the service \(for example, us\-east\-1\)\.  | The default AWS Region associated with the active credentials profile\. | 

## Example: Template launch configuration<a name="example-template"></a>

Here is an example launch configuration file for an AWS SAM template target:

```
{
    "configurations": [
        {
            "type": "aws-sam",
            "request": "direct-invoke",
            "name": "my-example:HelloWorldFunction",
            "invokeTarget": {
                "target": "template",
                "templatePath": "template.yaml",
                "logicalId": "HelloWorldFunction"
            },
            "lambda": {
                "payload": {},
                "environmentVariables": {}
            }
        }
    ]
}
```

## Example: Code launch configuration<a name="example-code"></a>

Here is an example launch configuration file for a Lambda function target:

```
{
    "configurations": [
        {
            "type": "aws-sam",
            "request": "direct-invoke",
            "name": "my-example:app.lambda_handler (python3.7)",
            "invokeTarget": {
                "target": "code",
                "projectRoot": "hello_world",
                "lambdaHandler": "app.lambda_handler"
            },
            "lambda": {
                "runtime": "python3.7",
                "payload": {},
                "environmentVariables": {}
            }
        }
    ]
}
```