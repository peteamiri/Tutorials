# Lambda

* [Goood Starting point](https://www.youtube.com/watch?v=abZYbBr1DNc)

* When Crating a Lambda fucntion you must assign a role to this function.
* You can select the following under the runtime;
  - Java (various versions)
  - NodeJS
  - Python
  - Go
  - .NET

* For Java based function,
  - Upload a package
  - identify what method of what class in what package to be executed.
    - The format is as  pakagename.classname::methodname
  - You can defiine environement variables
  - You cna assign amount of memory to use. The more momory the moore you pay.
  - Time out defines how long function can run for.
  - Netwrok sectrion you define:
    - VPC defualt is No VPC, means fundtion runs outside of VPC.
  - You define to capture regarding the failed execution

## Test Events

* is a test case for the function andd what values to be passed to it.
* test cases can be sunny day and rainy day sceneerio's
  - Valid Test
  - Invalid test
* the result provides the execution logs.
* Each execution has a log stream that is sent to Cloudwatch
* Monitoring tab provides an overview of execution.

# N-t

* [See this for more infotrmation](https://www.youtube.com/watch?v=Byhg9BBsbJw)