#How to install Debian 7

#get debian version
#apt-get install lsb-release(if not lsb_release)

lsb_release -da
#aptitude install sudo
#http://www.ducea.com/2006/05/18/install-sudo-on-debian/

apt-get install sudo
#настройка судо
#http://debian-help.ru/articles/ustanovka-i-nastroika-sudo-v-debian-7/
apt-get install curl

sudo apt-get install apache2
sudo service apache2 stop
sudo service apache2 start
sudo service apache2 restart

#install php 5.4

apt-get install php5-common libapache2-mod-php5 php5-cli

#more config controll
#http://php.net/manual/ru/install.unix.debian.php

#msql config addition
#https://habrahabr.ru/post/20736/
#sudo apt-get install php5 libapache2-mod-php5 libapache2-mod-auth-mysql php5-mysql php-image-graph imagemagick

#update php to 5.6


sudo nano /etc/apt/sources.list

#add

deb http://packages.dotdeb.org wheezy all
deb-src http://packages.dotdeb.org wheezy all
deb http://packages.dotdeb.org wheezy-php56-zts all
deb-src http://packages.dotdeb.org wheezy-php56-zts all

#save and run

sudo apt-get update
sudo apt-get upgrade
sudo apt-get install php5 