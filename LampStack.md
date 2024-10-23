# LAMP Stack Implementation on AWS

## Overview

This documentation captures my learning process and the steps I followed to implement a LAMP stack on AWS. I encountered challenges that tested my problem-solving skills and helped me grow as a developer, particularly in cloud infrastructure, web server management, and database integration.

This project involved launching an EC2 instance, setting up a secure web environment, and integrating Apache, MySQL, and PHP to create a dynamic web server. Below are the key steps, insights, and lessons learned during my self-study process.

---

## Step 1: Install Apache and Update the Firewall

### What I Did
The first step was installing Apache, a widely-used web server. I began by ensuring that all packages were up-to-date on the EC2 instance to avoid compatibility issues later on.

``` code
sudo apt update
sudo apt upgrade -y
``` 


Once the system was updated, I installed Apache using the following command:
```
sudo apt install apache2 -y
````
To make sure Apache starts on boot and is running as a service, I ran:
```
sudo systemctl enable apache2
sudo systemctl status apache2
````
! [photos a](Photos\a.png)
! [photos b](Photos\b.png)! [photos c](Photos\c.png)! [photos d](Photos\d.png)! [photos e](Photos\e.png)! [photos f](Photos\f.png)! [photos g](Photos\g.png)

! [Apache h](Photos\h.png)! [Apache i](Photos\i.png) ! [Apache j](Photos\j.png)! [Apache k](Photos\k.png) ! [Apache L](Photos\l.png) ! [Apache M](Photos\m.png) ! [Apache N ](Photos\n.png)! [Apache O](Photos\o.png)


## Problem-Solving Approach
When I first installed Apache, I wanted to test if it could serve pages to the public using the server’s public IP address. I attempted to access the Apache default page but realized that sometimes the security group settings would block traffic. By reviewing the inbound rules, I ensured port 80 (HTTP) and port 22 (SSH) were properly configured.

I also learned how to retrieve the public IP address programmatically using the command below:
```` 
curl -s http://169.254.169.254/latest/meta-data/public-ipv4
````
This step taught me to think holistically when configuring infrastructure—ensuring firewall rules, server configurations, and networking settings are correctly aligned.


# Step 2: Install MySQL
### What I Did
MySQL was the next key component of the LAMP stack, acting as the database management system. Here, I faced some challenges, especially around security configuration. I started with the MySQL installation:
```
sudo apt install mysql-server
```
Once installed, I checked MySQL’s status:
```
sudo systemctl enable --now mysql
sudo systemctl status mysql
```
#### Screenshots:
! [Sql P](Photos\p.png) ! [Sql Q](Photos\q.png) ! [Sql R](Photos\r.png) ! [Sql S ](Photos\s.png)! [Sql T](Photos\t.png)

### Problem-Solving Approach
One of the key issues I encountered was ensuring that MySQL was securely configured. By running the mysql_secure_installation script, I set a strong password for the root user and disabled anonymous users.
```
sudo mysql_secure_installation
````
The process of setting up MySQL with secure defaults taught me the importance of always being cautious about database security, especially when working with cloud-based systems where public access is a possibility.


# Step 3: Install PHP
### What I Did
With Apache and MySQL set up, the next step was to install PHP, the scripting language responsible for generating dynamic content. I installed PHP along with necessary modules for MySQL integration:
```` 
sudo apt install php libapache2-mod-php php-mysql
````
To confirm PHP was installed properly, I checked the PHP version:
````
php -v
```` 
#### Screenshots:

! [php U](Photos\u.png)
! [php V](Photos\v.png)
! [php W](Photos\w.png)! 
[php X](Photos\x.png)
! [php Y](Photos\y.png)
! [php Z](Photos\z.png) 

! [php Z1 ](Photos\z1.png) ! [php Z2](Photos\z2.png) ! [php Z3](Photos\z3.png) ! [php Z4](Photos\z4.png) ! [php Z5](Photos\z5.png)  ! [php Z6](Photos\z6.png)  ! [php Z7](Photos\z7.png) 


#### Problem-Solving Approach
After installing PHP, I created a test PHP file (index.php) to verify that Apache could serve dynamic content. This step helped me understand the importance of setting proper DirectoryIndex order in Apache’s configuration so that PHP files take precedence over HTML.
```
sudo vim /var/www/projectlamp/index.php

```` 
````
<?php
phpinfo();
?>
````
This was a critical learning moment, as I understood how web servers prioritize different types of files (HTML vs PHP) and how you can adjust configurations to suit your needs.


# Step 4: Create a Virtual Host for Apache
## What I Did
I wanted to go beyond a basic web server and configure a virtual host to manage multiple websites on a single server. This meant creating a custom directory for my project and configuring Apache to serve from this directory.
### 1. Create the Project Directory:
```
sudo mkdir /var/www/projectlamp
sudo chown -R $USER:$USER /var/www/projectlamp
````
### 2.Configure Apache to Serve the Virtual Host:
```
sudo vim /etc/apache2/sites-available/projectlamp.conf
```
I added the following configuration to define my virtual host:
```
<VirtualHost *:80>
    ServerName projectlamp
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
### 3.Enable the Site:
```
sudo a2ensite projectlamp.conf
sudo systemctl reload apache2
```
#### Screenshots:
##### 1. Virtual Host Configuration:

! [php Z8](Photos\z8.png) ! [php Z9](Photos\z9.png)! [php Z10](Photos\z10.png) ! [php Z11](Photos\z11.png)  

##### 2.Serving from Virtual Host:
! [php Z12](Photos\z12.png) ! [php Z13](Photos\z13.png) ! [php Z14](Photos\z14.png) ! [php Z15](Photos\z15.png)


### Problem-Solving Approach
Creating a virtual host was one of the more complex parts of the project. I initially ran into issues where the default Apache configuration would override my virtual host setup. After some troubleshooting, I realized that I needed to disable Apache’s default site using:
````
sudo a2dissite 000-default.conf
````
This challenge helped me better understand how Apache serves multiple sites and how to manage conflicts between them, a skill that will be valuable when working with large-scale hosting environments.


### Conclusion
Throughout this self-study process, I encountered numerous challenges that pushed me to think critically and troubleshoot effectively. From setting up secure environments to learning the intricacies of web server configurations, this project has solidified my understanding of LAMP stack development and deployment.

The experience has also enhanced my cloud management skills, particularly with AWS EC2, networking, and database security. By documenting each step and reflecting on the design choices and problem-solving approaches, I’ve gained insights that will certainly be useful for future projects.


