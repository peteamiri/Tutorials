# AWS API Gateway

* Provides a HTTP API 
* You can sent the following commands to AWS API Gateway;
  - Get
  - Put
  - Post
  - Delete

* You select the resource, it is simply the service name.
* You select action under that given resource. that is POST, GET, PUT, and Delete.

# Create a new API

To create an API you must select;

* Provide name
* Select actions
  - Create a Resource
  - you can select Lambda Function, HTTP, Mock, AWS Service, VPC Link.
  - Use Lambda Prxy Integration: makes it moore efficient... need to findout why?
  - Lambda Region (AWS region that lambda is executed)
  - Lambda function name
  - Use default timeout

# Deploying

* when done you need to deploy the API
