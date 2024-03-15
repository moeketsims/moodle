# Setting up Moodle

Before setting up Moodle, you might need to install Node.js if your Moodle plugins or themes require it. The following instructions are for Debian-based systems (like Ubuntu). They will download and execute a script from NodeSource (which provides Node.js packages) to add their repository, and then install Node.js.

```bash
# Add the NodeSource repository for Node.js 21.x
curl -fsSL https://deb.nodesource.com/setup_21.x | sudo -E bash -

# Install Node.js
sudo apt-get install -y nodejs

