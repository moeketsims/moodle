# Setting up Moodle

Before setting up Moodle, you might need to install Node.js if your Moodle plugins or themes require it. The following instructions are for Debian-based systems (like Ubuntu). They will download and execute a script from NodeSource (which provides Node.js packages) to add their repository, and then install Node.js.

```bash
# Add the NodeSource repository for Node.js 21.x
curl -fsSL https://deb.nodesource.com/setup_21.x | sudo -E bash -

# Install Node.js
sudo apt-get install -y nodejs
```
Adjust the Node.js version in the URL (`setup_21.x`) if a different version is required for your Moodle setup. This will help ensure users are getting the most relevant and secure version of Node.js for their needs.


