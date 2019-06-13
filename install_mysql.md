Install MySQL
=================
sudo apt-get update
sudo apt-get install mysql-server


Allow remote access
===================
sudo ufw allow mysql


Start the MySQL service
=======================
systemctl start mysql


Launch at reboot
================
systemctl enable mysql


Start the mysql shell
=====================
/usr/bin/mysql -u root -p

mysql>


Set the root password
=====================

For version MySQL < 5.7 
UPDATE mysql.user SET Password = PASSWORD('password') WHERE User = 'root';

For version MySQL >= 5.7 
UPDATE mysql.user SET authentication_string = PASSWORD('password') WHERE User = 'root';

FLUSH PRIVILEGES;


View users
==========
SELECT User, Host, authentication_string FROM mysql.user;



Create a database
=================

CREATE DATABASE demodb;


SHOW DATABASES;



Add a database user
====================
INSERT INTO mysql.user (User,Host,authentication_string,ssl_cipher,x509_issuer,x509_subject)
VALUES('demouser','localhost',PASSWORD('demopassword'),'','','');

FLUSH PRIVILEGES;

Verify that the user was created by running a SELECT query again:
SELECT User, Host, authentication_string FROM mysql.user;



Grant database user permissions
===============================


GRANT ALL PRIVILEGES ON demodb.* to demouser@localhost;

FLUSH PRIVILEGES;

SHOW GRANTS FOR 'demouser'@'localhost';














