# Task Fourteen - Web Server Setup on Cloud VM

## Description
This repository provides step-by-step instructions for setting up a web server on a cloud-hosted Virtual Machine (VM). The setup includes logging into the VM via SSH, cloning an HTML page, configuring Apache, installing PHP and MySQL, and building a registration and login system using PHP.

## Steps for Setting Up the Web Server

### 1. Log in to Your Cloud VM via SSH from Kali Linux
1. Open the Kali Linux terminal.
2. Use the following SSH command to log in to your VM:
   ```bash
   ssh -i /path-to-private_key username@<your-vm-public-ip>
3. **Screenshot**: Capture a screenshot showing a successful SSH login.

### 4. Clone the Repository from Task Twelve
1. After logging into the VM, clone your Task 12 repository from GitHub:
   ```bash
   git clone https://github.com/yourusername/tasktwelve.git
   ```

### 5. Copy Files to Apache Web Server Root Directory
1. Copy the HTML and related files from the cloned `tasktwelve` folder to the root directory of the Apache web server:
   ```bash
   sudo cp -r tasktwelve/* /var/www/html/
   ```

### 6. Start the Apache Web Server
1. Ensure Apache is installed. If not, install it using:
   ```bash
   sudo apt install apache2
   ```
2. Start the Apache web server:
   ```bash
   sudo systemctl start apache2
   ```
3. Verify that the Apache service is running:
   ```bash
   sudo systemctl status apache2
   ```

### 7. Access the Web Page via Browser
1. Open a web browser on your local machine and enter the public IP of your cloud VM:
   ```bash
   http://<your-vm-public-ip>
   ```
2. **Screenshot**: Capture a screenshot of the webpage being served from the cloud VM.

### 8. Install PHP and MySQL on the VM
1. If PHP and MySQL are not already installed, run the following commands:

   **Install PHP**:
   ```bash
   sudo apt update
   sudo apt install php libapache2-mod-php
   ```

   **Install MySQL**:
   ```bash
   sudo apt install mysql-server
   ```

### 9. Start MySQL Server and Log in
1. Start the MySQL service:
   ```bash
   sudo systemctl start mysql
   ```
2. Log in to MySQL as the root user:
   ```bash
   sudo mysql -u root -p
   ```

### 10. Create a Database, Table, and User in MySQL
1. Inside the MySQL shell, run the following commands to create a database, table, and user:

   **Create Database**:
   ```sql
   CREATE DATABASE userdb;
   USE userdb;
   ```

   **Create Users Table**:
   ```sql
   CREATE TABLE users (
       id INT AUTO_INCREMENT PRIMARY KEY, 
       username VARCHAR(50), 
       email VARCHAR(100), 
       password VARCHAR(255)
   );
   ```
2. **Screenshot**: Capture a screenshot showing the creation of the database, table, and user in MySQL.

### 11. Create a PHP Script for User Registration
1. Write a PHP registration script (`register.php`) that allows users to register with their username, email, and password. Ensure that the script inserts the data into the `users` table of the `userdb` database.
2. Access the registration page in your browser:
   ```bash
   http://<your-vm-public-ip>/register.php
   ```

### 12. Log in as the Registered User
1. After registering a new user, log in with the same credentials.
2. **Screenshot**: Capture a screenshot showing a successful login.

### 13. Share the Public IP of Your Web Server
1. Share the public IP of your web server with friends or colleagues to verify if they can access the registration and login pages.

### 14. Public IP
The public IP of my VM: `20.193.150.163`

