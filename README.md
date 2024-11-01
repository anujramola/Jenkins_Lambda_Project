# Jenkins_Lambda_Project

## Project Overview

The Jenkins Lambda Project automates the deployment of a serverless application hosted on AWS Lambda. It utilizes AWS SAM (Serverless Application Model) to build and manage the serverless application and Jenkins as the CI/CD tool to streamline the process from code commit to deployment.

## Installation Prerequisites

1. AWS Account
2. AWS CLI
3. Python 3.x
4. AWS SAM CLI
5. Jenkins
6. Git
7. Python Virtual Environment

### Why Use AWS SAM for Jenkins Deployment

**AWS Serverless Application Model (SAM)** is used in this project for its advantages:

1. **Simplified Deployment**: SAM makes it easy to deploy AWS Lambda functions and API Gateway with simple configuration files.
  
2. **Infrastructure as Code**: SAM allows us to define our application’s infrastructure in a YAML template, promoting better version control and collaboration.

3. **Local Testing**: Developers can test and debug functions locally, simulating the AWS environment.

4. **CI/CD Integration**: SAM works well with Jenkins, enabling automated builds, tests, and deployments for quick updates.

5. **Version Control**: Managing application code and infrastructure together simplifies tracking changes and rollbacks.

### What is AWS SAM?

AWS SAM is an open-source framework for building serverless applications on AWS. It lets you:

- Define resources in a YAML file.
- Package and deploy applications easily using the SAM CLI.
- Test functions locally.

### How SAM Helps Manage Source Code

AWS SAM helps manage source code by:

- **Unified Configuration**: Storing code and infrastructure definitions together for easier collaboration.
- **Version Control**: Tracking changes in a single repository improves organization.
- **Continuous Integration**: Ensures automatic deployments with each code change, reducing errors.

***To build the sam application using sam cli:***
***aws configure : provide access key and secret key here***
SAM Basics steps are: 

***sam init***
![sam-init](output_screenshots/sam_init.png)

***sam build***
![sam-build](output_screenshots/sam_build.png)

***sam deploy --stack-name <name_of_stack>***
![sam-deploy](output_screenshots/sam_deploy.png)

***Get the url from console***
![get-url](output_screenshots/url.png)

***URL GUI***
![get-output](output_screenshots/hello_world.png)


### Why Use Jenkins for Deploying AWS Lambda Functions

1. **Automated CI/CD**:
   - Jenkins automates the integration and deployment of code changes for AWS Lambda functions, speeding up development and reducing errors.

2. **Streamlined Deployments**:
   - It sets up automated pipelines that handle the entire deployment process, from building code to pushing updates to AWS.

3. **Integration with Version Control**:
   - Jenkins works well with Git, allowing automatic deployments when new code is pushed, ensuring the latest changes are deployed.

4. **Scalability**:
   - It can manage deployments for multiple Lambda functions, making it easier to handle growth and complexity in serverless applications.

5. **Monitoring and Reporting**:
   - Jenkins provides visibility into the deployment process, helping teams quickly identify and fix issues.

### Use Cases for Companies

- **Faster Releases**: Companies can roll out new features and updates quickly, keeping up with customer needs.
- **Better Collaboration**: Automated testing and deployment reduce bottlenecks, improving teamwork.
- **Consistent Environments**: Ensures AWS Lambda functions are deployed uniformly across development, testing, and production, minimizing errors.

Using Jenkins for AWS Lambda deployments makes the process more efficient, reliable, and scalable, enhancing the overall software development lifecycle.

***Jenkins-build***
![all the jenkins stages](output_screenshots/jenkins-build.png)

***Jenkins console URL***
![Jenkins Console URL](output_screenshots/jenkins-url.png)

***Jenkins Console Output***
![URL output for pipeline run by jenkins](output_screenshots/hello-world-jenkins.png)

***verifying lambda function on aws***
![verifying lambda function on aws](output_screenshots/aws-lambda.png)

***verifying lambda logs using cloudwatch service in aws***
![verifying lambda logs using cloudwatch service in aws](output_screenshots/aws-cloudwatch-logs.png)

***Cloudformation-stack for lambda function***
![Cloudformation-stack for lambda function](output_screenshots/aws-cloudformation.png)

***Api-gateway***
![api-gateway verification for lambda function](output_screenshots/aws-api-gateway.png)

**To delete all the resources using samcli**
![deleteing all the resources](output_screenshots/sam-delete.png)
