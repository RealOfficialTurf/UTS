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
 