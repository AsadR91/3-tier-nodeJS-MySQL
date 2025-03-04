3-Tier NodeJS-MySQL Application Setup
This guide outlines the steps to set up and run a 3-tier NodeJS application with a MySQL database.

Prerequisites
NodeJS: Ensure NodeJS is installed on your system. Installation instructions can be found at Nodejs.org/en/download/package-manager.

Setup Instructions
Clone the Repository:

Create a working directory and clone the repository:

bash
mkdir 3-tier-nodejs-MYSQL
cd 3-tier-nodejs-MYSQL
git clone https://github.com/AsadR91/3-tier-nodeJS-MySQL
NodeJS Configuration:

Install NVM (Node Version Manager):

bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
Important: After running the above command, copy and execute the environment variable commands provided in the output to properly initialize NVM in your shell. These commands will typically resemble the following:

bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
Install NodeJS (Version 22):

bash
nvm install 22
MySQL Server Setup:

Update Package Repository:

bash
sudo apt update
Install MySQL Server:

bash
sudo apt install mysql-server
Configure Root Password (MySQL 8+):

sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
FLUSH PRIVILEGES;
Create Database:

sql
CREATE DATABASE test_db;
