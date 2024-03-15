# Setting up Moodle

Before setting up Moodle, you might need to install Node.js if your Moodle plugins or themes require it. The following instructions are for Debian-based systems (like Ubuntu). They will download and execute a script from NodeSource (which provides Node.js packages) to add their repository, and then install Node.js.

## Updating Ubuntu System

Before installing any new software, it's a good practice to update your system to ensure all existing packages are up to date. This can improve security and compatibility. Run the following commands in your terminal:

```bash
# Update the list of available packages and their versions
sudo apt-get update

# Install newer versions of the packages you have
sudo apt-get upgrade -y
```

## Installing Nodejs
```bash
# Add the NodeSource repository for Node.js 21.x
curl -fsSL https://deb.nodesource.com/setup_21.x | sudo -E bash -

# Install Node.js
sudo apt-get install -y nodejs
```
Adjust the Node.js version in the URL (`setup_21.x`) if a different version is required for your Moodle setup. This will help ensure users are getting the most relevant and secure version of Node.js for their needs.

# Upgrading npm

npm, the Node Package Manager, is a crucial tool for managing dependencies in Node.js projects. To ensure you have the latest features and security updates, it's important to keep npm up-to-date. Follow the steps below to upgrade npm on your system.

## Windows

For Windows users, the best way to upgrade npm is to re-download and install Node.js from the [official website](https://nodejs.org/). This process will automatically upgrade npm along with Node.js.

## macOS and Linux

For macOS and Linux users, you can upgrade npm to the latest version by running the following command in your terminal:

```bash
sudo npm install -g npm@latest
```

# Installing the AWS Cloud Development Kit (CDK)
The AWS CDK allows you to define your cloud resources in a familiar programming language. To install the AWS CDK, ensure you have Node.js and npm installed, then run the following command
```bash
sudo npm install -g aws-cdk
```
## Check CDK is Installed
```bash
cdk --version
```
# Pull the source code into your machine by running the following in your terminal:
```bash
git clone https://github.com/aws-samples/aws-cdk-ecs-refarch-moodle.git
```
# Change Directory
Ensure you have docker running and then change the director as indicated below
```bash
cd aws-cdk-ecs-refarch-moodle/src
```
# Build Moodle Image
To build Moodle docker image with the name moodleimage run 
```bash
docker build -t moodleimage image/src
```
# Authenticating with Amazon ECR

To push or pull images from Amazon Elastic Container Registry (ECR), you must authenticate your Docker client to the registry. These instructions assume you have already installed the AWS CLI and Docker on your machine.

## Prerequisites

- AWS CLI: Ensure you have the [AWS CLI](https://aws.amazon.com/cli/) installed and configured with the appropriate access credentials and default region.
- Docker: Make sure [Docker](https://www.docker.com/) is installed on your system.

## Authenticating Docker to Amazon ECR

1. Retrieve the authentication token and authenticate your Docker client to the registry using the AWS CLI:

    ```bash
    aws ecr get-login-password --region <your-region> | docker login --username AWS --password-stdin <your-account-id>.dkr.ecr.<your-region>.amazonaws.com
    ```

    Replace `<your-region>` with your AWS region (e.g., `us-west-2`) and `<your-account-id>` with your AWS account ID.

2. After successfully authenticating, you can push or pull images using Docker commands. For example, to push an image to your
