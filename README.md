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
npm install -g aws-cdk
```

