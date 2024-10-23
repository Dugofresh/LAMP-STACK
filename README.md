# LAMP Stack Implementation on AWS

This project showcases the complete implementation of a LAMP (Linux, Apache, MySQL, PHP) stack on an AWS EC2 instance. The project was completed as part of a self-study to understand and deploy web servers in cloud environments. By following these steps, you'll be able to replicate the LAMP stack on your own AWS instance and understand key concepts in server setup, database integration, and virtual hosting.

## Project Overview

- **Project Type:** AWS Cloud-based LAMP Stack Implementation
- **Skills Demonstrated:** Cloud infrastructure management (AWS EC2), web server setup (Apache), database management (MySQL), dynamic scripting (PHP), and security configurations
- **Repository URL:** [https://github.com/Dugofresh/LAMP-STACK.git](https://github.com/Dugofresh/LAMP-STACK.git)

## Key Features

- **Apache**: Installed and configured as the web server to serve dynamic PHP content.
- **MySQL**: Used as the database management system.
- **PHP**: Handles server-side scripting for dynamic website functionality.
- **Virtual Host Configuration**: Set up a virtual host to manage multiple websites on a single server.
- **Security**: Configured firewall and MySQL security settings to ensure safe access to the services.

## What I Learned

- Configuring EC2 instances on AWS to host a LAMP stack.
- Managing firewall rules to secure web traffic (HTTP, SSH).
- Setting up a MySQL database and integrating it with PHP.
- Deploying a basic dynamic website using Apache and PHP.
- Configuring a virtual host to serve content from a custom directory.
- Troubleshooting and problem-solving Apache, MySQL, and PHP issues.

## Technologies Used

- **Operating System**: Ubuntu 20.04 (Linux)
- **Web Server**: Apache
- **Database**: MySQL
- **Scripting Language**: PHP
- **Cloud Provider**: AWS EC2

## Setup Instructions

To replicate this project, follow the steps below:

1. **Launch EC2 Instance on AWS**
   - Use the free-tier eligible Ubuntu instance.
   - SSH into the instance using your key pair.

2. **Install Apache**
   ```bash
   sudo apt update
   sudo apt install apache2 -y
   ```
   
3. **Install MySQL**
  ```
sudo apt install mysql-server -y
````


4. **Install PHP**
````
sudo apt install php libapache2-mod-php php-mysql -y
```

### Design Choices & Problem-Solving.
The main goal was to ensure the LAMP stack was set up in a secure and efficient manner. Throughout the project, I focused on security by:

Setting up firewall rules to allow only necessary traffic (HTTP and SSH).
Running mysql_secure_installation to lock down MySQL from remote access.
Creating a virtual host to ensure clean management of multiple web projects in the future.
I also learned how to resolve common issues like Apache’s default configuration overriding my custom setup. This required disabling the default site with:



