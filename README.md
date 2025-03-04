3-Tier NodeJS-MySQL Application Setup
This guide outlines the steps to set up and run a 3-tier NodeJS application with a MySQL database.

Prerequisites
NodeJS: Ensure NodeJS is installed on your system. Installation instructions can be found at Nodejs.org/en/download/package-manager.

Setup Instructions
Clone the Repository:

Create a working directory and clone the repository:


mkdir 3-tier-nodejs-MYSQL
cd 3-tier-nodejs-MYSQL
git clone https://github.com/AsadR91/3-tier-nodeJS-MySQL
NodeJS Configuration:

Install NVM (Node Version Manager):


curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash

Important: After running the above command, copy and execute the environment variable commands provided in the output to properly initialize NVM in your shell. These commands will typically resemble the following:


export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
Install NodeJS (Version 22):


nvm install 22

MySQL Server Setup:

Update Package Repository:


sudo apt update

Install MySQL Server:

sudo apt install mysql-server

You can connect to the sql for the first time using, it shouldn't ask for the password. 

sudo mysql -u root

Configure Root Password (MySQL 8+):

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
FLUSH PRIVILEGES;

Create Database:

CREATE DATABASE test_db;

MySQL Database and Table Setup
View Existing Databases:

sql
SHOW DATABASES;
Access the "test_db" Database:

sql
USE test_db;
Create the "users" Table:

sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    role ENUM('Admin', 'User') NOT NULL
);
Exit MySQL client.

Application Setup and Deployment

Configure Client:

cd client
npm install
npm run build


Configure Server:

cd ../server
npm install
npm start
The application should now be accessible at http://localhost:5000 (replace "localhost" with your server's IP address if necessary).

Data Verification
After entering data through the application UI:

Access MySQL:

mysql -u [username] -p
View and Select Database:

SHOW DATABASES;
USE test_db;
Verify Data Entry:


SELECT * FROM users;

This query should display the data entered via the application interface.





