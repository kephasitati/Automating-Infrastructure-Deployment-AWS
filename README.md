# Automating Infrastructure Deployment in AWS

This guide provides step-by-step instructions for deploying and managing infrastructure in AWS using AWS CloudFormation and CodePipeline. The tasks covered include creating an S3 bucket, configuring it as a static website, storing templates in a version control system (Challenge #2), cloning a CodeCommit repository, creating a new network layer, defining an EC2 instance resource, and duplicating the deployment to another AWS Region.

## Task 1: Creating an AWS CloudFormation Template

1. Open the AWS Cloud9 IDE.
2. Create an AWS CloudFormation template named `S3.yaml`.
3. Use the following AWS CLI commands to create an S3 bucket:
   ```bash
   aws configure get region
   aws cloudformation create-stack --stack-name CreateBucket --template-body file://S3.yaml
   ```
4. Verify the stack creation in the AWS CloudFormation service.

## Task 2: Configuring the Bucket as a Website and Updating the Stack

1. Update the `S3.yaml` template to configure the S3 bucket as a static website.
2. Add an output to the template providing the website URL.
3. Browse to the AWS CloudFormation service and confirm the stack update completed successfully.

## Challenge #2: Storing Templates in a Version Control System

### Task 3: Cloning a CodeCommit Repository

1. Browse to the CodeCommit service.
2. Clone the `CFTemplatesRepo` repository to the AWS Cloud9 workspace.
3. Analyze the contents of the `start-lab.yaml` file in the repository.

## Task 4: Creating a New Network Layer with AWS CloudFormation, CodeCommit, and CodePipeline

1. Create a new AWS CloudFormation template (`cafe-network.yaml`) for a VPC, public subnet, and other resources.
2. Analyze the preconfigured AWS CodePipeline details.
3. Trigger the pipeline by pushing the `cafe-network.yaml` template to CodeCommit.
4. Confirm the stack creation/update in the AWS CloudFormation console.

## Task 5: Updating the Network Stack

1. Update the network stack to export essential information.
2. Save changes, commit, and push the updates to CodeCommit.
3. Verify the stack update and check the Outputs tab for export names.

## Task 6: Defining an EC2 Instance Resource and Creating the Application Stack

1. Duplicate `template2.yaml` as `cafe-app.yaml`.
2. Define a new parameter for choosing instance types.
3. Create an EC2 instance resource with specific characteristics.
4. Save the changes, validate the template, and push it to CodeCommit.
5. Confirm the successful update of the `update-cafe-app` stack in AWS CloudFormation.

## Task 7: Duplicating the Café Network and Website to Another AWS Region

1. Use AWS CLI to duplicate the café network to another region.
2. Confirm the stack creation in the AWS CloudFormation console.
3. Create an EC2 key pair in the new region (e.g., Oregon).
4. Copy the `cafe-app.yaml` template to an S3 bucket.
5. In the Oregon region, create a new stack using the updated template.
6. Access the café website in both regions using the respective public IP addresses.

Congratulations! You have successfully automated infrastructure deployment in AWS using AWS CloudFormation, CodeCommit, and CodePipeline.
