# Step 5 - Enable PHP on the website
With the default DirectoryIndex setting on Apache, index.html file will always take precedence over index.php file. This is useful for setting up maintenance page in PHP applications, by creating a temporary index.html file containing an informative message for visitors. The index.html then becomes the landing page for the application. Once maintenance is over, the index.html is renamed or removed from the document root bringing back the regular application page. If the behaviour needs to be changed, /etc/apache2/mods-enabled/dir.conf file should be edited and the order in which the index.php file is listed within the DirectoryIndex directive should be changed.

### 1. Open the dir.conf file with vim to change the behaviour
! [php](Photos\z8.png)

! [php](Photos\z9.png)

! [php](Photos\z10.png)



### 2. Reload Apache
! [php](Photos\z11.png)

### 3. Create a php test script to confirm that Apache is able to handle and process requests for PHP files.

! [php](Photos\z12.png)

! [php](Photos\z13.png)


### 4. Now refresh the page
! [php](Photos\z14.png)

! [php](Photos\z15.png)