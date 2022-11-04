# install apache2 server on ubuntu 20.04 LTS

- Install

```bash
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install apache2
```



- Check

```bash
$ apache2 -v
$ netstat -ntlp

```


- Control

```bash
$ sudo service apache2 restart
$ sudo service apache2 stop
$ sudo service apache2 start
```

- Change root path

```bash
$ sudo vi /etc/apache2/sites-available/000-default.conf

     DocumentRoot /var/www/html

$ sudo vi /etc/apache2/apache2.conf

     <Directory /workplace>
             Options Indexes FollowSymLinks
             AllowOverride None
             Require all granted
     </Directory>

$ sudo service apache2 restart
```

### (optional) install php

```bash
     $ sudo apt-get install php
```
