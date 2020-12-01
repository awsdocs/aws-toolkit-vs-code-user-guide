# Troubleshooting serverless applications<a name="serverless-apps-troubleshooting"></a>

This topic details common errors that you might encounter when creating serverless applications with the Toolkit for VS Code and how to resolve them\.

**Topics**
+ [Error: "RuntimeError: Container does not exist"](#troubleshooting-container-does-not-exist)
+ [Error: "docker\.errors\.APIError: 500 Server Error \.\.\. You have reached your pull rate limit\."](#troubleshooting-reached-rate-limit)
+ [Error: "500 Server Error: Mounting C:\\Users\\\.\.\."](#troubleshooting-mounting-error)
+ [Using WSL, webviews \(for example, the "Invoke on AWS" form\) are broken](#troubleshooting-broken-webviews)

## Error: "RuntimeError: Container does not exist"<a name="troubleshooting-container-does-not-exist"></a>

The `sam build` command can show this error if your system does not have enough disk space for the Docker container\. If your system storage has only 1\-2 GB of space available, `sam build` might fail during processing, even if system storage is not completely full before the build starts\. For more information, see [this GitHub issue](https://github.com/aws/aws-sam-cli/issues/2121)\.

## Error: "docker\.errors\.APIError: 500 Server Error \.\.\. You have reached your pull rate limit\."<a name="troubleshooting-reached-rate-limit"></a>

Docker Hub limits requests that anonymous users can make\. If your system reaches the limit, Docker fails and this error appears in the OUTPUT view of VS Code:

```
docker.errors.APIError: 500 Server Error: Internal Server Error ("toomanyrequests: You have
reached your pull rate limit. You may increase the limit by authenticating and upgrading:
https://www.docker.com/increase-rate-limit")
```

Ensure that your system Docker service has authenticated with your Docker Hub credentials\.

## Error: "500 Server Error: Mounting C:\\Users\\\.\.\."<a name="troubleshooting-mounting-error"></a>

Windows users might see this Docker mounting error when debugging AWS SAM applications:

```
Fetching lambci/lambda:nodejs10.x Docker container image......
2019-07-12 13:36:58 Mounting C:\Users\<username>\AppData\Local\Temp\ ... as /var/task:ro,delegated inside runtime container
Traceback (most recent call last):
...
requests.exceptions.HTTPError: 500 Server Error: Internal Server Error ...
```

Try refreshing the credentials for your shared drives \(in the Docker settings\)\.

## Using WSL, webviews \(for example, the "Invoke on AWS" form\) are broken<a name="troubleshooting-broken-webviews"></a>

This is a known VS Code issue for users of Cisco VPN\. For more information, see [this GitHub issue](https://github.com/aws/aws-toolkit-vscode/issues/1327)\.

A workaround is suggested in [this WSL tracking issue](https://github.com/microsoft/WSL/issues/4277)\.