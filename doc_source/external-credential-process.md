# Using an external credential process<a name="external-credential-process"></a>

If you have a process to generate or lookup credentials that isn't directly supported by AWS, you can configure the AWS Toolkit for VS Code to use that process instead of any [stored AWS credentials](aws-credentials.md)\.

The method for specifying such an external credential process is the same as for the AWS CLI, and consists of adding a `credential_process` definition to your *shared AWS conﬁg file*\. For detailed information about how to do this, see [Sourcing Credentials with an External Process](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-sourcing-external.html) in the *AWS Command Line Interface User Guide*\.