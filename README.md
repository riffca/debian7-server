#How to install Debian 7

```bash
apt-get install sudo
apt-get install curl

```

##nodejs
```bash
curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -
sudo apt-get install -y nodejs
```

## Sudo settings
http://debian-help.ru/articles/ustanovka-i-nastroika-sudo-v-debian-7/


```bash

sudo apt-get install apache2
sudo service apache2 stop
sudo service apache2 start
sudo service apache2 restart
```

##New host not default:80 port and same domain

https://www.digitalocean.com/community/tutorials/apache-ubuntu-14-04-lts-ru
https://serversforhackers.com/configuring-apache-virtual-hosts

check default host file

```bash
nano /etc/apache2/sites-available/default
```
create new dir and host file
```bash
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
##mysql

```bash
	apt-get purge mysql-server mysql-client
	//solve err
	//mysql-server-5.5
```
##phpmyadmin
```bash
sudo apt-get install phpmyadmin
sudo nano /etc/apache2/apache2.conf
//Include /etc/phpmyadmin/apache.conf
sudo service apache2 restart

```

http://dbadiaries.com/how-to-install-mysql-5-5-on-ubuntu-server-12-04-lts

```bash
sudo apt-get install mysql-server
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

```
##ad ftp-server(lunix adduser)
http://iantonov.me/page/ustanovka-i-nastrojka-vsftpd-v-debian-7
http://askubuntu.com/questions/410244/a-command-to-list-all-users-and-how-to-add-delete-modify-users

```bash
apt-get install vsftpd

```

##composer install
http://onedev.net/post/176
```bash
cd ~
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/bin/composer
```

##module rewrite
http://ru.stackoverflow.com/questions/47021/%D0%9A%D0%B0%D0%BA-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%B8%D1%82%D1%8C-mod-rewrite


##Issues
https://www.howtoforge.com/community/threads/mysql-server-problem-after-upgrading.65479/

##linux copy folder
http://www.cyberciti.biz/faq/copy-folder-linux-command-line/


##Создать дизайн
http://younglinux.info/book/export/html/10


##Показ всех файлов
```bash
http://stackoverflow.com/questions/1019116/using-ls-to-list-directories-and-their-total-sizes
```
##Mysql новые пользователи
http://www.liquidweb.com/kb/create-a-mysql-user-on-linux-via-command-line/
```bash
mysql -u root -p
```
##Все команды в одном файле

write
```bash
/dir/#cat comands
```
run

```
/dir/#sh comands
```bash

##shh screen оставляем процессы в интернете
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-screen-on-an-ubuntu-cloud-server

http://help.ubuntu.ru/wiki/screen



##Proxypass
http://geckich.blogspot.ru/2011/11/modproxy-apache.html
http://www.tech-notes.net/proxypass-requests-with-apache/

##Фронтенд на ngnix
https://habrahabr.ru/post/120814/


##ngnix на frontend
https://habrahabr.ru/post/120814/
##Скрипт для управления host на ngnix
https://habrahabr.ru/post/202348/
