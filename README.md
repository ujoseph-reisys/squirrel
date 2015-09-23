SQUIRREL WHISPERERS
===================
Austin’s own Squirrel Whisperers are poised for breakout success with the release of their latest single, “Devops Overlord,” receiving heavy airplay on regional radio stations and online streaming services.

Prerequisites
--------------

- Oracle Virtualbox
- Vagrant 

Deployment with Vagrant
-------------------------

Assumptions
```
- host folder => /var/www/sqbox
- target folder => /var/www/
```

Steps
```
	- cd /var/www/ 
	- git clone https://github.com/ullasjos/squirrel.git sqbox
	- cd sqbox/VagrantBox 
	- vagrant up
```

Note: default IP will be 192.168.56.109 
add the following line in the host file of your local machine

192.168.56.109 local.sqbox 
to your local machine's host entry

type http://local.sqbox in your address bar and the site will be up.

You can always change the configuration settings like host and target folder, IPs etc in config.yaml file - https://github.com/ullasjos/squirrel/blob/master/VagrantBox/puphpet/config.yaml
eg) IP you can change at line #11 private_network: 192.168.56.1xx
source and target at line# 37 and 38 respectively


Deployment - Old fashioned way
--------------------------------
Assumptions
```
- LAMP already installed with necessary PHP modules - curl, gd library etc.
- NPM installed
```

Steps
```
	- Login to your mysql server as root
	- CREATE USER 'myadmin'@'localhost' IDENTIFIED BY 'password';
	- GRANT ALL PRIVILEGES ON * . * TO 'myadmin'@'localhost'; //or the necessary permissions u want
	- mysql -umyadmin -ppasswrod;
	- create dabatabse squirrel_db;
	- exit;
	- mysql -umyadmin -ppasswrod squirrel_db < /scripts/db/squirrel_db.sql
    (if you are changing, the databasename and credentials please update sites/all/default/settings.php accordingly)
```
