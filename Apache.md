# Step 1 - Install Apache and Update the Firewall
### Update and upgrade the list of packages in the package manager:

sudo apt update

sudo apt upgrade -y
! [Apache](Photos\h.png)
! [Apache](Photos\i.png)
! [Apache](Photos\j.png)

## Run Apache2 package installation:
!! [Apache](Photos\k.png)

3. ###  Enable and verify that apache is running on as a service on the OS.
! [Apache](Photos\l.png)

sudo systemctl enable apache2

sudo systemctl status apache2

4. ### The server is running and can be accessed locally in the ubuntu shell by running the command below:
! [Apache](Photos\m.png)

! [Apache](Photos\n.png)

5. ### Test with the public IP address if the Apache HTTP server can respond to request from the internet using the url on a browser.

! [Apache](Photos\o.png)

