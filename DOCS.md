# INTRODUCTION

This is a documentation file for our midterm exam, how to configure LEMP Stack and Server Configuration.

## Package Installation:
1) Update Software Repo &  Install Nginx files
```shell
 sudo apt-get update
 sudo apt get install nginx mariadb-server mariadb-client php7.2 php7.2-fpm
```
2) Start nginx, mysql and php services 
```shell
 sudo service nginx start
 sudo service php7.2-fpm start
 sudo service mysql start
```
3) Check Local ip & Run MariaDb Post-Installation script
```shell
 curl -4 icanhazip.com
 sudo mysql_secure_installation
```

## Nginx Server Setup:
1) Change Directory to /etc/nginx/sites-available
2) Duplicate the default file and name it midtest
```shell
 sudo cp default midtest
```
3) Entering root, so you won't need to write sudo everytime :)
```shell
 sudo su
```
4) Open default file in nano
```shell
 nano default
```
5) Change Configuration file & Test Configration
```shell
 nginx -t
```
6) Create Symbolic link and unlink previous
```shell
ln -s/etc/nginx/sites-available/midtest /etc/nginx/sites-enabled
unlink /etc/nginx/sites-enabled/default
```
7) Reload nginx server
```shell
 service nginx reload
```
8) Create info.php file directory /var/www/html, add <?php phpinfo(); ?>
9) Rollback, should have used midtest not default
10) Remove the wrong file(default) and create new copy
``shell
rm default
cp midtest default
```
11) Configure the server again
```shell
nano midtest
```
12) Check the configuration again & remove the previous link file
```shell
nginx -t
rm /etc/nginx/sites-available/midtest
```
13) Create new Symbolic link
```shell
 ln -s/etc/nginx/sites-available/midtest/etc/nginx/sites-enabled
```
14) Reload nginx Server again

## Lion Wiki
1) Download Lion Wiki with wget, Download Unzip
```shell
 wget http://lionwiki.0o.cz/download/3.2.11/lionwiki-3.2-11.zip
 apt install unzip 
```
2) make ./var folder write-able
```shell
 chmod 777 /var -R
```
## Upload/Submission
1) Installing git, clone repo, change directory
```shell
 get apt install git
 git clone https://github.com/RealOfficialTurf/UTS.git
 cd UTS
```
2) Initialize Git folder and copy var to folder
```shell
 cp /var/www/html/lionwiki-3.2-11 . -R
 mv ./lionwiki-3.2-11/var .
```
3) Add to staging, commit changes, push
```shell
 git add var
 git commit -m "added /var"
 git push origin master
```

