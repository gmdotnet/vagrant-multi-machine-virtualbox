# VAGRANT BOXES

### MySQL server
- created an user called `local` (password `local`) with root privilegies
- root password is `vagrant` (in box version >= 1.1.0 user `root` can only login through unix socket)

### Apache server
- ServerName is `vagrant`
- daemon user is `vagrant`
- root folder is `/var/www`
- mod_rewrite and mod_vhost_alias enabled
- IMPORTANT: you need to add `EnableSendfile Off` on your website configuration under <Directory "..."> </Directory> ( here all info  https://www.vagrantup.com/docs/synced-folders/virtualbox.html )
- All website must be `*.vagrant` because main server name is `vagrant`, if you want to change please edit `/etc/apache2/ports.conf`

### PHP Xdebug
- auto-activated in PHP cli and PHP "web"
- IDEKEY = "VAGRANT"
- uncomment `xdebug.remote_host` in `php.ini` to enable your IDE for remote xdebug

### SMTP and EMAIL with postfix and MailHog
- postfix is configured as satellite system with 127.0.0.1:1025
- mailhog do not start automatically. Just open a shell and type `mailhog`
    - web interface is set on `<vagrant ip>:8025`
- all emails are not sent outside the machine
- to test:
    - start mailhog
    - send a test email with `echo "this is a test email | mail -s "subject test email" fake@fake.mail`
    - check on your browser `<vagrant ip>:8025` the email sent
- you can use mailhog as SMTP server, just configure your application to send email at 127.0.0.1 with port 1025

### Other info
- root password is `vagrant` but you can simply run `sudo su` from vagrant user
- if you can't find a configuration in this file before, it means is used the default value

---

## VERSIONS 

### Box code: `giuseppemorelli/lamp-stack`

## 1.1.0

**OS**: debian/stretch 9.3.0  64bit

- apache2  2.4.25
- [composer](https://getcomposer.org/)  1.6.2
- curl  7.52.1
- git  2.11.0
- [git up](https://github.com/msiemens/PyGitUp) (plugin for git - python version)   1.4.6
- htop
- iotop
- jpegoptim 1.4.4
- mailutils
- [mailhog](https://github.com/mailhog/MailHog)  1.0.0
- mc (midnight commander)
- mariadb  10.1.26
- mysqltuner 1.6.18
- optipng 0.7.6
- phpmyadmin 4.7.7 - all languages
- pip (python package manager)
- redis server
- tig

- Magento Utils:
  - [modman](https://github.com/colinmollenhour/modman) 1.12
  - [n98-magerun](https://github.com/netz98/n98-magerun)  1.100.0
  - [n98-magerun2](https://github.com/netz98/n98-magerun2) 2.0.0  

- PHP
  - php7.0   7.0.27
  - php7.0-cli
  - php7.0-dev
  - php7.0-gd
  - php7.0-intl
  - php7.0-mcrypt
  - php7.0-mysql
  - php7.0-mbstring
  - php7.0-xml
  - php7.0-xsl
  - php7.0-zip
  - php7.0-json
  - php7.0-xdebug
  - php7.0-soap
  - php-pear
  
- [Node.js](https://nodejs.org/en/) 6.9.1 LTS
  - [bower](https://bower.io/)  1.8.0
  - [grunt](http://gruntjs.com/)  1.0.1
  - [grunt-cli](http://gruntjs.com/)  1.2.0
  - [gulp-cli](http://gulpjs.com/)  1.2.2    

---

## 1.0.3

**OS**: debian/jessie 8.6.1  64bit

- apache2  2.4.10
- [composer](https://getcomposer.org/)  1.2.3
- curl 7.38.0
- git 2.1.4
- [git up](https://github.com/msiemens/PyGitUp) (plugin for git - python version) 1.4.4
- htop
- jpegoptim 1.4.1
- mailutils
- [mailhog](https://github.com/mailhog/MailHog)  0.2.1
- mc-dbg (midnight commander)
- mysql percona 5.7
- mysqltuner 1.6.18
- optipng 0.7.5
- phpmyadmin 4.6.5.2 - all languages
- pip (python package manager)
- postfix
- redis server
- [sass](http://sass-lang.com/)  3.4.22
- tig
- [webgrind](https://github.com/jokkedk/webgrind) 1.4.0

- Magento Utils:
  - [modman](https://github.com/colinmollenhour/modman) 1.12
  - [n98-magerun](https://github.com/netz98/n98-magerun)  1.97.24
  - [n98-magerun2](https://github.com/netz98/n98-magerun2)  1.3.0

- PHP
  - php7.0   7.0.13
  - php7.0-cli
  - php7.0-curl
  - php7.0-dev
  - php7.0-gd
  - php7.0-intl
  - php7.0-mcrypt
  - php7.0-mysql
  - php7.0-mbstring
  - php7.0-xml
  - php7.0-xsl
  - php7.0-zip
  - php7.0-json
  - php7.0-xdebug
  - php7.0-soap
  - php-pear

- [Node.js](https://nodejs.org/en/) 6.9.1 LTS
  - [bower](https://bower.io/)  1.8.0
  - [CSS Lint](http://csslint.net/)  1.0.5
  - [grunt](http://gruntjs.com/)  1.0.1
  - [grunt-cli](http://gruntjs.com/)  1.2.0
  - [gulp-cli](http://gulpjs.com/)  1.2.2    
  - [LESS](http://lesscss.org/)  2.7.1
  - [npm](https://www.npmjs.com/)  3.10.8

---

## 1.0.2

**OS**: debian/jessie 8.6.1  64bit
 
- apache2  2.4.10
- [composer](https://getcomposer.org/)  1.2.3
- curl 7.38.0
- git
- [git-up](https://github.com/aanand/git-up/) (plugin for git)
- htop
- jpegoptim 1.4.1
- mailutils
- [mailhog](https://github.com/mailhog/MailHog)  0.2.0
- mc-dbg (midnight commander)
- mysql-server 5.5.53
- mysqltuner 1.6.18
- optipng 0.7.5
- phpmyadmin 4.6.5.1 - all languages (accessible via *http://phpmyadmin.vagrant* on your file host with the same ip of vagrant machine)
- postfix
- [sass](http://sass-lang.com/)  3.4.22
- tig
- xdebug

- Magento Utils:
 - [modman](https://github.com/colinmollenhour/modman) 1.12
 - [n98-magerun](https://github.com/netz98/n98-magerun)  1.97.24

- PHP
  - php5  5.6.27
  - php5-cli
  - php5-curl
  - php5-dev
  - php5-gd
  - php5-intl
  - php5-mcrypt
  - php5-mysql
  - php-pear

- [Node.js](https://nodejs.org/en/) 4.4.7
  - [npm](https://www.npmjs.com/)  2.15.8
  - [bower](https://bower.io/)  1.7.9
  - [LESS](http://lesscss.org/)  2.7.1
  - [CSS Lint](http://csslint.net/)  1.0.2
  - [grunt-cli](http://gruntjs.com/)  1.2.0
  - [grunt](http://gruntjs.com/)  1.0.1

-----

## 1.0.1 - deprecated

(not available anymore)

**OS**: debian/jessie 8.5.1  64bit
 
- apache2  2.4.10
- [composer](https://getcomposer.org/)  1.2.0
- curl
- git
- [git-up](https://github.com/aanand/git-up/) (plugin for git)
- htop
- jpegoptim 1.4.1
- mailutils
- [mailhog](https://github.com/mailhog/MailHog)  0.2.0
- mc-dbg (midnight commander)
- mysql-server 5.5
- mysqltuner 1.6.0
- optipng 0.7.5
- phpmyadmin 4.6.3 - all languages (accessible via *http://phpmyadmin.vagrant* on your file host with the same ip of vagrant machine)
- postfix
- [sass](http://sass-lang.com/)  3.4.22
- tig
- xdebug

- Magento Utils:
 - [modman](https://github.com/colinmollenhour/modman) 1.12
 - [n98-magerun](https://github.com/netz98/n98-magerun)  1.97.22

- PHP
 - php5  5.6
 - php5-cli
 - php5-curl
 - php5-dev
 - php5-gd
 - php5-intl
 - php5-mcrypt
 - php5-mysql
 - php-pear

- [Node.js](https://nodejs.org/en/) 4.4.7
 - [npm](https://www.npmjs.com/)  2.15.8
 - [bower](https://bower.io/)  1.7.9
 - [LESS](http://lesscss.org/)  2.7.1
 - [CSS Lint](http://csslint.net/)  1.0.2
 - [grunt-cli](http://gruntjs.com/)  1.2.0
 - [grunt](http://gruntjs.com/)  1.0.1
     
-----