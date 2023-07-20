# What is devOps
DevOps is a software development methodology that aims to integrate the work of software development and IT teams by automating and streamlining the processes between them. It involves using practices, tools, and a cultural philosophy to unite people, processes, and technology in application planning, development, delivery, and maintenance. The goal is to remove the barriers between traditionally siloed teams , allowing for seamless collaboration and faster delivery of high-quality software.

# DevOps vs. CI/CD

DevOps and CI/CD are related but different concepts. CI/CD is a set of practices that are part of the DevOps methodology. CI/CD refers to the continuous integration and continuous delivery/deployment of application changes , automation of build, testing, and deployment pipelines. DevOps is a cultural, practice-driven philosophy focused on collaboration and communication between development and operations teams. DevOps includes many concepts beyond CI/CD, such as infrastructure as code, monitoring, and testing. In summary, CI/CD is a subset of DevOps that focuses on the automated building, testing, and deployment of code changes.

In summary, CI/CD and DevOps are related but different concepts. CI/CD (Continuous Integration/Continuous Delivery) refers to a set of practices and tools for automating the building, testing, and deployment of code changes . It's a subset of the broader DevOps methodology, which involves a cultural, practice-driven philosophy focused on collaboration and communication between development and operations teams. DevOps includes many other concepts beyond CI/CD, such as infrastructure as code, monitoring, and testing.

CI/CD refers to a set of development practices that enable the rapid and reliable delivery of code changes, while DevOps is a collection of ideas, practices, processes, and technologies that allow development and operations teams to work together to streamline product development.



## Read more

* [DevOps vs. CI/CD]()

# What is CI/CD
CI/CD stands for Continuous Integration/Continuous Delivery (or Continuous Deployment). It is a software development approach that involves frequent and automated testing, integration, and delivery of code changes to production environments. Continuous Integration (CI) is the practice of frequently merging code changes into a shared repository and running automated tests to detect and fix defects early on in the development process. Continuous Delivery (CD) is the practice of deploying code changes to production environments automatically and regularly, ensuring that code changes are delivered quickly, safely and reliably. Together, CI/CD helps teams deliver high-quality software faster and more efficiently.

## Read More

  * [GitLab](https://about.gitlab.com/topics/ci-cd/)


# Continuous Integration
Continuous Integration (CI) is the practice used by development teams of automating, merging, and testing code. CI helps to catch bugs early in the development cycle, which makes them less expensive to fix. Automated tests execute as part of the CI process to ensure quality. CI systems produce artifacts and feed them to release processes to drive frequent deployments.

# Continuous Delivery
Continuous Delivery (CD) is a process by which code is built, tested, and deployed to one or more test and production environments. Deploying and testing in multiple environments increases quality. CD systems produce deployable artifacts, including infrastructure and apps. Automated release processes consume these artifacts to release new versions and fixes to existing systems. Systems that monitor and send alerts run continually to drive visibility into the entire CD process.

# Continuous Testing
Whether your app is on-premises or in the cloud, you can automate build-deploy-test workflows and choose the technologies and frameworks. Then, you can test your changes continuously in a fast, scalable, and efficient manner. Continuous testing offers the following benefits.

Maintain quality and find problems as you develop. Continuous testing with Azure DevOps Server ensures your app still works after every check-in and build, enabling you to find problems earlier by running tests automatically with each build.

Use any test type and any test framework. Choose your preferred test technologies and frameworks.

View rich analytics and reporting. When your build is done, review your test results to resolve any issues. Actionable build-on-build reports let you instantly see if your builds are getting healthier. But it's not just about speed - detailed and customizable test results measure the quality of your app.

# Key Concepts

* A trigger tells a Pipeline to run.
* A pipeline is made up of one or more stages. A pipeline can deploy to one or more environments.
* A stage is a way of organizing jobs in a pipeline and each stage can have one or more jobs.
* Each job runs on one agent. A job can also be agentless.
* Each agent runs a job that contains one or more steps.
* A step can be a task or script and is the smallest building block of a pipeline.
* A task is a pre-packaged script that performs an action, such as invoking a REST API or publishing a build artifact.
* An artifact is a collection of files or packages published by a run.

### Agent
When your build or deployment runs, the system begins one or more jobs. An agent is computing infrastructure with installed agent software that runs one job at a time. For example, your job could run on a Microsoft-hosted Ubuntu agent.

## Approvals
Approvals define a set of validations required before a deployment runs. Manual approval is a common check performed to control deployments to production environments. When checks are configured on an environment, pipelines will stop before starting a stage that deploys to the environment until all the checks are completed successfully.

## Artifact
An artifact is a collection of files or packages published by a run. Artifacts are made available to subsequent tasks, such as distribution or deployment.

## Continuous delivery
Continuous delivery (CD) is a process by which code is built, tested, and deployed to one or more test and production stages. Deploying and testing in multiple stages helps drive quality. Continuous integration systems produce deployable artifacts, which include infrastructure and apps. Automated release pipelines consume these artifacts to release new versions and fixes to existing systems. Monitoring and alerting systems run constantly to drive visibility into the entire CD process. This process ensures that errors are caught often and early.

##  Continuous integration
Continuous integration (CI) is the practice used by development teams to simplify the testing and building of code. CI helps to catch bugs or problems early in the development cycle, which makes them easier and faster to fix. Automated tests and builds are run as part of the CI process. The process can run on a set schedule, whenever code is pushed, or both. Items known as artifacts are produced from CI systems. They're used by the continuous delivery release pipelines to drive automatic deployments.

## Deployment
For Classic pipelines, a deployment is the action of running the tasks for one stage, which can include running automated tests, deploying build artifacts, and any other actions are specified for that stage.


## Deployment group
A deployment group is a set of deployment target machines that have agents installed. A deployment group is just another grouping of agents, like an agent pool. You can set the deployment targets in a pipeline for a job using a deployment group. Learn more about provisioning agents for deployment groups.

## Environment
An environment is a collection of resources, where you deploy your application. It can contain one or more virtual machines, containers, web apps, or any service that's used to host the application being developed. A pipeline might deploy the app to one or more environments after build is completed and tests are run.

## Job
A stage contains one or more jobs. Each job runs on an agent. A job represents an execution boundary of a set of steps. All of the steps run together on the same agent. Jobs are most useful when you want to run a series of steps in different environments. For example, you might want to build two configurations - x86 and x64. In this case, you have one stage and two jobs. One job would be for x86 and the other job would be for x64.

## Pipeline
A pipeline defines the continuous integration and deployment process for your app. It's made up of one or more stages. It can be thought of as a workflow that defines how your test, build, and deployment steps are run.

## Release
For Classic pipelines, a release is a versioned set of artifacts specified in a pipeline. The release includes a snapshot of all the information required to carry out all the tasks and actions in the release pipeline, such as stages, tasks, policies such as triggers and approvers, and deployment options. You can create a release manually, with a deployment trigger, or with the REST API.


## Run
A run represents one execution of a pipeline. It collects the logs associated with running the steps and the results of running tests. During a run, Azure Pipelines will first process the pipeline and then send the run to one or more agents. Each agent will run jobs. Learn more about the pipeline run sequence.

## Script
A script runs code as a step in your pipeline using command line, PowerShell, or Bash. You can write cross-platform scripts for macOS, Linux, and Windows. Unlike a task, a script is custom code that is specific to your pipeline.

## Stage
A stage is a logical boundary in the pipeline. It can be used to mark separation of concerns (for example, Build, QA, and production). Each stage contains one or more jobs. When you define multiple stages in a pipeline, by default, they run one after the other. You can specify the conditions for when a stage runs. When you are thinking about whether you need a stage, ask yourself:

Do separate groups manage different parts of this pipeline? For example, you could have a test manager that manages the jobs that relate to testing and a different manager that manages jobs related to production deployment. In this case, it makes sense to have separate stages for testing and production.

Is there a set of approvals that are connected to a specific job or set of jobs? If so, you can use stages to break your jobs into logical groups that require approvals.

Are there jobs that need to run a long time? If you have part of your pipeline that will have an extended run time, it makes sense to divide them into their own stage.

## Step
A step is the smallest building block of a pipeline. For example, a pipeline might consist of build and test steps. A step can either be a script or a task. A task is simply a pre-created script offered as a convenience to you. To view the available tasks, see the Build and release tasks reference. For information on creating custom tasks, see Create a custom task.

## Task
A task is the building block for defining automation in a pipeline. A task is packaged script or procedure that has been abstracted with a set of inputs.

## Trigger
A trigger is something that's set up to tell the pipeline when to run. You can configure a pipeline to run upon a push to a repository, at scheduled times, or upon the completion of another build. All of these actions are known as triggers. For more information, see build triggers and release triggers.

## Library
The Library includes secure files and variable groups. Secure files are a way to store files and share them across pipelines. You may need to save a file at the DevOps level and then use it during build or deployment. In that case, you can save the file within Library and use it when you need it. Variable groups store values and secrets that you might want to be passed into a YAML pipeline or make available across multiple pipelines.

# Devops DevSecOps

* [Wiki](https://en.wikipedia.org/wiki/DevOps)
* [DevOps Definition](https://theagileadmin.com/what-is-devops/)

# MicroSoft DevOps

* [Documentation](https://docs.microsoft.com/en-us/azure/devops/learn/)

## Resources

* [BookMark](http://www.devopsbookmarks.com/)
* [ToolSet](https://newrelic.com/devops/toolset)
* [Devop Resource](https://www.janbasktraining.com/blog/devops-tutorial/)
* [DevOps Tutorial](https://www.javainuse.com/devOps)
* [CI/CD](https://dzone.com/devops-tutorials-tools-news)

# List of Common Tools

* Infrastructure Automation
  - Chef,
  - Puppet,
  - Ansible,
  - Salt

* Build Tools
  - Maven,
  - Gradle,
  - Ant,
  - NAnt,
  - MSBuild,
  - Rake,
  - GNU Make

* SCM Tools
  - SVN,
  - Git,
  - Perforce,
  - Mercurial

* Continuous Integration Tools
  - Jenkins,
  - Cruise,
  - TeamCity,
  - Bamboo,
  - Hudson

* Continuous Delivery
  - GoCD,
  - CA Release Automation,

* Security
  - OWASP,
  - Veracode,
  - Fortify

* Containerization
  - Docker,
  - Kubernetes,
  - Mesos

* Scripting Languages
  - Shell Script,
  - Ruby/JRuby,
  - Perl,
  - Python,
  - PowerShell

* Application Servers, servlet containers, and web servers
  - Weblogic,
  - Tomcat,
  - JBoss

* Agile Tools
  - Rally,
  - Jira,
  - Version One

* Document repository
  - Confluence

* Code Quality
  - SonarQube (Open Source)
