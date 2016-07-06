#How to install Debian 7

```bash
apt-get install sudo
```

## Sudo settings
http://debian-help.ru/articles/ustanovka-i-nastroika-sudo-v-debian-7/


```bash
apt-get install curl

sudo apt-get install apache2
sudo service apache2 stop
sudo service apache2 start
sudo service apache2 restart
```

##New host not default:80 port and same domain

https://www.digitalocean.com/community/tutorials/apache-ubuntu-14-04-lts-ru

check default host file

```bash
nano /etc/apache2/sites-available/default
```
create new dir and host file
sudo mkdir /var/www/test.com/public
nano /var/www/test.com/public/index.html
nano /etc/apache2/sites-available/test.com.conf
```
host example
```xml

	listen 2111
	<VirtualHost *:2111>
	    #ServerAdmin riffca@ya.ru
	    #ServerName riffca.pserver.ru(доменное имя)
	    #ServerAlias www.pserver.ru
	    DocumentRoot /var/www/example.com/public
	    ErrorLog ${APACHE_LOG_DIR}/error.log
	    CustomLog ${APACHE_LOG_DIR}/access.log combined
	</VirtualHost>

```

##run port

```bash
sudo a2ensite test.com.conf
sudo service apache2 restart
```
##создание отличных IP адресов

```bash
nano etc/hosts
185.118.164.55 riffca.pserver.ru
```
##install php 5.4

```bash
apt-get install php5-common libapache2-mod-php5 php5-cli

//more config controll
http://php.net/manual/ru/install.unix.debian.php

```

##mysql addition
https://ariejan.net/2007/12/12/how-to-install-mysql-on-ubuntudebian/
http://linux-notes.org/ustanovka-mysql-na-debian-ubuntu-linux-mint/
https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-debian
http://iantonov.me/page/nastraivaem-lamp-linux-apache-mysql-php-v-debian-7
```bash
sudo apt-get install php5 libapache2-mod-php5 libapache2-mod-auth-mysql php5-mysql php-image-graph imagemagick
```
##update php to 5.6
https://habrahabr.ru/post/20736/

```bash
sudo nano /etc/apt/sources.list
```
add text

```bash
deb http://packages.dotdeb.org wheezy all
deb-src http://packages.dotdeb.org wheezy all
deb http://packages.dotdeb.org wheezy-php56-zts all
deb-src http://packages.dotdeb.org wheezy-php56-zts all

```
save and run

```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install php5 

``