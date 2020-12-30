# Running and debugging local Amazon API Gateway resources<a name="debug-apigateway"></a>

You can run or debug AWS SAM API Gateway local resources, specified in `template.yaml`, by running a VS Code launch config of `type=aws-sam` with the `invokeTarget.target=api`\.

**Note**  
API Gateway supports two types of APIs, REST and HTTP\. However, the API Gateway feature with the AWS Toolkit for Visual Studio Code only supports REST APIs\. Sometimes HTTP APIs are called "API Gateway V2 APIs\."

**To run and debug local API Gateway resources**

1.  Choose one of the following approaches to create a launch config for an AWS SAM API Gateway resource: 
   + **Option 1:** Visit the handler source code \(\.js, \.cs, or \.py file\) in your AWS SAM project, hover over the Lambda handler, and choose the **Add Debug Configuration** CodeLens\. Then, in the menu, choose the item marked **API Event**\.
   + **Option 2:** Edit `launch.json` and create a new launch configuration using the following syntax\.

     ```
     {
       "type": "aws-sam",
       "request": "direct-invoke",
       "name": "myConfig",
       "invokeTarget": {
         "target": "api",
         "templatePath": "n12/template.yaml",
         "logicalId": "HelloWorldFunction"
       },
       "api": {
         "path": "/hello",
         "httpMethod": "post",
         "payload": {
           "json": {}
         }
       }, 
       "sam": {},
       "aws": {}
     }
     ```

1. In the VS Code **Run** panel, choose the launch config \(named `myConfig` in the above example\)\.

1. \(Optional\) Add breakpoints to your Lambda project code\.

1.  Type **F5** or choose **Play** in the **Run** panel\. 

1. In the output pane, view the results\. 

## Configuration<a name="apigateway-configuration"></a>

When you use the `invokeTarget.target` property value `api`, the Toolkit changes the launch configuration validation and behavior to support an `api` field\. 

 

```
{
  "type": "aws-sam",
  "request": "direct-invoke",
  "name": "myConfig",
  "invokeTarget": {
    "target": "api",
    "templatePath": "n12/template.yaml",
    "logicalId": "HelloWorldFunction"
  },
  "api": {
    "path": "/hello",
    "httpMethod": "post",
    "payload": {
      "json": {}
    },
    "querystring": "abc=def&qrs=tuv",
    "headers": {
        "cookie": "name=value; name2=value2; name3=value3"
    }
  },
  "sam": {},
  "aws": {}
}
```

Replace the values in the example as follows:

**invokeTarget\.logicalId**  
An API resource\.

**path**  
The API path that the launch config requests, for example, `"path": "/hello"`\.  
Must be a valid API path resolved from the `template.yaml` specified by `invokeTarget.templatePath`\.

**httpMethod**  
One of the following verbs: "delete", "get", "head", "options", "patch", "post", "put"\.

**payload**  
The JSON payload \(HTTP body\) to send in the request , with the same structure and rules as the [lambda\.payload](https://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/serverless-apps-run-debug-config-ref.html) field\.  
`payload.path` points to a file containing the JSON payload\.  
`payload.json` specifies a JSON payload inline\.

**headers**  
Optional map of name\-value pairs, which you use to specify HTTP headers to include in the request, as shown in the following example\.  

```
"headers": {
     "accept-encoding": "deflate, gzip;q=1.0, *;q=0.5",
     "accept-language": "fr-CH, fr;q=0.9, en;q=0.8, de;q=0.7, *;q=0.5",
     "cookie": "name=value; name2=value2; name3=value3",
     "user-agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.198 Safari/537.36",
}
```

**querystring**  
Optional string which sets the `querystring` of the request, for example, `"querystring": "abc=def&ghi=jkl"`\.

**aws**  
How AWS connection information is provided\. For more information, see the **AWS connection \("aws"\) properties** table in the [Configuration options for debugging serverless applications](serverless-apps-run-debug-config-ref.md) section\.

**sam**  
How the AWS SAM CLI builds the application\. For more information, see the **AWS SAM CLI \("sam"\) properties** table in the [Configuration options for debugging serverless applications](serverless-apps-run-debug-config-ref.md) section\.