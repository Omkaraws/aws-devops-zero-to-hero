Certainely AWS lambda is a serverless computing service which provides by aws. it allows you to run code without provisioning/ managing servers. with lambda you can focus on your application code, and aws take care of the infra, scaling & servers maintainance.

Important Terms Used in Lambda:


a. Function: a function is a resource that you can invoke to run your code in AWS lambda. A function has code that processes events and a runtime that passes request and responses between lambda and the function code.

b. Runtime: lambda runtimes allows functions in different languages to run in the same base execution environment. The runtime sits in between the lambda service and your function code relying invocation events, context information and responses between the two.

c. Event: it is a JSON formatted document that contains data for a function to process.

d. Event Source/ Trigger: an AWS service such as Amazon SNS or a custom service that triggers your function and executes its logic.

e. Downstream Resource: an AWS service, such as Dynamo DB tables or S3 buckets that your lambda function call once it is triggered.

f. Concurrency: number of request that your function is serving in any given time

### 1. What is AWS Lambda?
AWS Lambda is a serverless compute service that lets you run code without provisioning or managing servers. It automatically scales and manages the infrastructure required to run your code in response to events.

### 2. How does AWS Lambda work?
You can upload your code to Lambda and define event sources that trigger the execution of your code. Lambda automatically manages the execution environment, scales it as needed, and provides monitoring and logging.

### 3. What are the key benefits of using AWS Lambda?
The benefits of AWS Lambda include automatic scaling, reduced operational overhead, cost efficiency (as you pay only for the compute time used), and the ability to build event-driven architectures.

### 4. What types of events can trigger AWS Lambda functions?
AWS Lambda functions can be triggered by various event sources, such as changes in Amazon S3 objects, updates to Amazon DynamoDB tables, HTTP requests through Amazon API Gateway, and more.

### 5. How is concurrency managed in AWS Lambda?
Lambda automatically handles concurrency by scaling out instances of your function in response to incoming requests. You can set a concurrency limit to control how many concurrent executions are allowed.

### 6. What is the maximum execution duration for a single AWS Lambda invocation?
The maximum execution duration for a single Lambda invocation is 15 minutes.

### 7. How do you pass data to and from AWS Lambda functions?
You can pass data to Lambda functions through event objects, which contain information about the triggering event. You can also return data by using the return statement or creating a response object.

### 8. Can AWS Lambda functions communicate with external resources?
Yes, Lambda functions can communicate with external resources such as databases, APIs, and other AWS services by using appropriate SDKs and APIs provided by AWS.

### 9. What are AWS Lambda layers?
AWS Lambda layers are a way to manage and share code that is common across multiple functions. Layers can include libraries, custom runtimes, and other function dependencies.

### 10. How can you handle errors in AWS Lambda functions?
You can handle errors by using try-catch blocks in your code. Lambda also provides CloudWatch Logs for monitoring, and you can set up error handling and retries for asynchronous invocations.

### 11. Can AWS Lambda functions access the internet?
Yes, Lambda functions can access the internet through the Virtual Private Cloud (VPC) or through public endpoints if your function is not configured within a VPC.

### 12. What are the execution environments available for AWS Lambda functions?
Lambda supports several runtimes, including Node.js, Python, Java, Go, Ruby, .NET Core, and custom runtimes using the Runtime API.

### 13. How can you configure environment variables for AWS Lambda functions?
You can set environment variables for Lambda functions when creating or updating the function. These variables can be accessed within your code.

### 14. What is the difference between synchronous and asynchronous invocation of Lambda functions?
Synchronous invocations wait for the function to complete and return a response, while asynchronous invocations return immediately, and the response is sent to a specified destination.

### 15. What is the AWS Lambda Event Source Mapping?
Event Source Mapping allows you to connect event sources like Amazon DynamoDB streams or Amazon Kinesis streams to Lambda functions. This enables the function to process events as they occur.

### 16. How can you manage the permissions and execution roles for AWS Lambda functions?
You can use AWS Identity and Access Management (IAM) roles to grant permissions to your Lambda functions. Execution roles define what AWS resources the function can access.

### 17. What is AWS Step Functions?
AWS Step Functions is a serverless orchestration service that lets you coordinate multiple AWS services into serverless workflows using visual workflows called state machines.

### 18. How can you automate the deployment of AWS Lambda functions?
You can use AWS Serverless Application Model (SAM) templates, AWS CloudFormation, or CI/CD tools like AWS CodePipeline to automate the deployment of Lambda functions.

### 19. Can AWS Lambda functions connect to on-premises resources?
Yes, Lambda functions can connect to on-premises resources by placing the function inside a VPC and using a VPN or Direct Connect connection to establish connectivity.

### 20. What is the Cold Start issue in AWS Lambda?
The Cold Start issue occurs when a Lambda function is invoked for the first time or after it has been idle for a while. The function needs to be initialized, causing a slight delay in response time.



## AWS lambda is a compute service that lets you run the code without provisioning or managing servers.
 With AWS lambda, you can run code for virtually any type of application or backend service- all with zero administration.
 AWS lambda manages all the administration it manages:
 Provisioning and capacity of the compute fleet that offers a balance of memory, CPU, network and other resources.
 Server and O.S maintenance
 High availability and automatic scaling
 Monitoring fleet health
 Applying security patches
 Deploying your code
 Monitoring and logging your lambda functions.
 AWS lambda runs your code on a high-availability compute infrastructure.
 AWS lambda runs your code on a high availability compute infrastructure.
 AWS lambda executes your code only when needed and scales automatically form a few requests per day to thousands per seconds.
 You pay only for the compute time, you consume no charge when your code is not running.
 All you need to do is supply your code in the form of one or more lambda functions to AWS lambda, in one of the languages that AWS supports (currently Node.js, java, powershell, C#, Ruby, Python and Go) and the service can run the code on your behalf.
 Typically the lifecycle for an AWS lambda based application includes authoring code, deploying code to AWS lambda and then monitoring and troubleshooting.
 This is in exchange for flexibility, which means you cannot log into compute instances or customize the operating system of language runtime.
 If you do want to manage your own compute, you can use EC2 of Elastic Beanstalk.

How Lambda Works:
 First you upload your code to lambda in one or more lambda function.
 AWS lambda will then execute the code in your behalf.
 After the code is invoked, lambda automatically take care of provisioning and managing the required servers.


Difference between AWS Lambda and EC2:
AWS Lambda:
 AWS lambda is a platform-as-a-service.
 It supports only limited languages like Node.js, python, java, C#, Ruby, Go and powershell.
 Write your code and push the code into AWS lambda.
 You cannot log into compute instances, choose customized O.S or language platform.


AWS EC2:
 AWS EC2 is an infrastructure—as-a-service.
 No environment restrictions, you can run any code or language.
 For the first time in EC2, you have to choose the O.S and install all the software required and then push your code in EC2.
 You can select variety of O.S, instance types, network and security patches, RAM and CPU etc.


Important Terms Used in Lambda:
a. Function: a function is a resource that you can invoke to run your code in AWS lambda. A function has code that processes events and a runtime that passes request and responses between lambda and the function code.

b. Runtime: lambda runtimes allows functions in different languages to run in the same base execution environment. The runtime sits in between the lambda service and your function code relying invocation events, context information and responses between the two.

c. Event: it is a JSON formatted document that contains data for a function to process.

d. Event Source/ Trigger: an AWS service such as Amazon SNS or a custom service that triggers your function and executes its logic.

e. Downstream Resource: an AWS service, such as Dynamo DB tables or S3 buckets that your lambda function call once it is triggered.

f. Concurrency: number of request that your function is serving in any given time.


When Lambda Triggers:
 You can use AWS lambda to run your code in response to :
 Events such as changes to data in an Amazon S3 or an Amazon Dynamo DB table.
 To run your code in response to HTTP request using Amazon API gateway.
 With the capabilities you can use lambda to easily build data processing triggers for AWS services like Amazon S3, and Amazon Dynamo DB process streaming data stored in kinesis or create your own backend that operates at AWS scale, performance and security.
Example of S3:
 The user create an object in a bucket.
 Amazon S3 invokes your lambda functions using the permission provided by the execution role.
 Amazon S3 knows which lambda function to invoke based on the event source mapping that is stored in the bucket notification configuration.


AWS Lambda Function Configuration:
 A lambda function consists of code and any associated dependencies.
 In addition a lambda function also has configuration information associated with it.
 Initially you specify the configuration information when you create a lambda function.
 Lambda provides an API for you to update some of the configuration data.


Lambda function configuration information includes the following key elements:
 Compute resources that you need you only specify the amount of memory you want to allocate from your lambda function.
 AWS lambda allocates CPU power proportional to the memory by using the same ratio as a general purpose Amazon EC2 instance type, such as an M3 type.
 You can update the configuration and request additional memory in 64mb increments from 128mb to 3008mb.
 Functions larger than 1536mb are allocated multiple CPU threads.


Maximum Execution Timeout:
 You pay for the AWS resources that are used to run your lambda function.
 To prevent your lambda function from running indefinitely, you specify a timeout.
 When the specified timeout is reached, AWS lambda terminates your lambda function.
 Default is 3sec and maximum is 9000sec (15min).
 IAM ROLE: this is the role that AWS lambda assume when it executes the lambda function on your behalf.


AWS Lambda Function- Services it can access:
 Lambda function can access:
 AWS services and non-AWS services.
 AWS services running in AWS VPC (e.g: redshift, elastic cache, RDS instance)
 Non-AWS services running on instances in an AWS VPC.
 AWS lambda run your function code securely with in a VPC by default.
 However to enable your lambda function to access resources inside your private VPC you must provide additional VPC specific configuration information that includes VPC subnet ID and Security group IDs
Different way to invoke Lambda Function:
1. Synchronous invoke (push)
2. Asynchronous invoke (event)
3. Poll-based invoke (pull based)
  
1. Synchronous Invoke:
 Synchronous invoke are the most straight forward way to invoke your lambda function. In this model your functions execute immediately when you perform the lambda invoke API call.
 Invocation flag specifies a value of “request-response”.
 You wait for the function to process the event and return a response.
Here is a list of services that invoke lambda function synchronously:
 Elastic Load Balancer
 Amazon Cognito
 Cloud front
 API Gateway
 Amazon Lex
 Kinesis data firehose

3. Asynchronous Invoke:
 For asynchronous invocation, lambda places the event in a queue and returns a success response without additional information.
 Lambda queues the event for processing and returns a response immediately.
 You can configure lambda to send an invocation record to another service like SQS, SNS, lambda and eventbridge.
Here is a list of services that invoke lambda function asynchronously:
 Amazon S3
 Amazon SNS
 SES
 Cloud watch logs
 Cloud watch events
 AWS code commit
 AWS config
4. Poll-Based Invoke:
The invocation model is designed to allow you to integrate with AWS stream and queue based service with no code or server management lambda will poll the following service on your behalf, retrieve records and invoke your function. The following are supported service:
 Amazon Kinesis
 Amazon SQS
 Amazon Dynamo DB Streams
