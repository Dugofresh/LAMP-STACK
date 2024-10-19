## WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS

### Introduction

The LAMP stack is a popular open-source web development platform that consists of four main components: Linux, Apache, MySQL, and PHP (or sometimes Perl or Python). This documentation outlines the setup, configuration, and usage of the LAMP stack.

## Step 0: Prerequisites

1. An EC2 Instance of t2.micro type and Ubuntu 24.04 LTS (HVM) was launched in the us-east-1 region using the AWS console.  
   ![Launch Instance](Photos\a.png)
    ![Security Rules](Photos\b.png)
     ![Default Network](Photos\c.png)

2. Created SSH key pair named **project1-key** to access the instance on port 22.


3. The security group was configured with the following inbound rules:
   - Allow traffic on port 80 (HTTP) with source from anywhere on the internet.
   - Allow traffic on port 443 (HTTPS) with source from anywhere on the internet.
   - Allow traffic on port 22 (SSH) with source from any IP address. This is opened by default.  
   ! [Port](Photos\d.png)
! [Port](Photos\e.png)
  

4. The default VPC and Subnet were used for the networking configuration.  
  

5. The private SSH key that got downloaded was located, permission was changed for the private key file and then used to connect to the instance by running:  
   ```bash
   chmod 400 project1-key.pem
   ssh -i "project1-key.pem" ubuntu@16.171.3.157

! [Port](Photos\e.png)
! [Port](Photos\g.png)

