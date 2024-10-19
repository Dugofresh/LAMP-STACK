# Step 3 - Install PHP
1. Install php Apache is installed to serve the content and MySQL is installed to store and manage data. PHP is the component of the set up that processes code to display dynamic content to the end user.

The following were installed:

php package
php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases.
libapache2-mod-php, to enable Apache to handle PHP files.

! [php](Photos\u.png)
! [php](Photos\v.png)
! [php](Photos\w.png)

## Step 4 - Create a virtual host for the website using Apache
! [php](Photos\x.png)

! [php](Photos\z.png)

### 3. Show the new file in sites-available
! [php](Photos\z1.png)

### 4. Enable the new virtual host
! [php](Photos\z2.png)

### 5. Disable apache’s default website.
! [php](Photos\z3.png)

### 6. Ensure the configuration does not contain syntax error
! [php](Photos\z4.png)

### 7. Reload apache for changes to take effect.
! [php](Photos\z5.png)

### 8. The new website is now active but the web root /var/www/projectlamp is still empty. Create an index.html file in this location so to test the virtual host work as expected.
! [php](Photos\z6.png)

### 9. Open the website on a browser using the public IP address.
! [php](Photos\z7.png)
