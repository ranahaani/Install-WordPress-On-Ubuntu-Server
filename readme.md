## Install WordPress with LAMP on Ubuntu server

Install WordPress on Ubuntu server with the terminal in 5 easy steps

#### 1) Update Ubuntu packages

Use apt to update and upgrade ubuntu dependencies 

```bash
sudo apt update
sudo apt upgrade -y
```

#### 2) Install apache server, MariaDB, php php-mysql php-cli php-common php-gd


```bash
sudo apt install apache2 mariadb-server mariadb-client php php-mysql php-cli php-common php-gd -y
```



#### 3) Download, extract, copy to var/www/html and change ownership of WordPress


```bash
wget https://wordpress.org/latest.tar.gz
tar -xvzf latest.tar.gz
sudo cp -r wordpress/* /var/www/html
sudo chown www-data:www-data -R /var/www/html
#remove index.html (apache default index file)
sudo rm -rf /var/www/html/index.html
```


#### 4) Setup MariaDB

```bash
sudo mysql_secure_installation
```



#### 5) Login to MySQL and create database

```bash
sudo mysql -u root -p
```

```mysql
create database wordpress;
create user "admin"@"%" identified by "password"
grant all privileges on wordpress.* to "admin"@"%"
```
access your ```IP``` or ```domain``` name and fill the database details and install WordPress 


## Watch full tutorial on youtube
[Install Wordpress On AWS EC2 Ubuntu Server Using Terminal](https://www.youtube.com/watch?v=3pMygVjLW3g)

