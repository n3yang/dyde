# DYDE (Docker Yii2 Development Environment)
Easy way for creating yii2 framework development environment with docker compose.

About Yii2 framework
* [Yii2 framework](https://www.github.com/yiisoft/yii2)

Images to used:  
* [Nginx](https://hub.docker.com/_/nginx/)
* [PHP](https://hub.docker.com/_/php/)
* [MariaDB(MySQL)](https://hub.docker.com/_/mariadb/)
* [Redis](https://hub.docker.com/_/redis/)

Requirement
-----------
* [Docker](https://docs.docker.com/engine/installation/)
* [Docker compose](https://docs.docker.com/compose/install/)

Usage
------------

1. Clone from github
```bash
git clone git@github.com:n3yang/dyde.git
```

2. Prepare enviroment

* Copy dyde.env to .env
* Edit .evn file, change some variables you want. (Optional)

3. Run

Rebuid PHP image, install extensions and composer
```bash
docker-compose up -d
```

4. Create yii2 project

```bash
docker exec -it dyde_php_1 composer create-project --prefer-dist yiisoft/yii2-app-basic .
```
The "dyde_php_1" is PHP container's name in your project.

5. Update MySQL password in yii2 config file. (Optional)

Enter PHP container
```bash
docker exec -it dyde_php_1 /bin/bash
```

Run
```bash
sed -i "s/mysql:host=localhost;dbname=yii2basic/mysql:host=mariadb;dbname=$MYSQL_DATABASE/" /var/www/html/config/db.php \
    && sed -i "s/'password' => ''/'password' => '$MYSQL_ROOT_PASSWORD'/" /var/www/html/config/db.php
```

Visit http://localhost:8000/ (default nginx http port)

Tree of directiory
------------------

```
.
├── app
├── conf
│   ├── mysql
│   │   └── tuning.cnf
│   ├── nginx
│   │   └── default.conf
│   └── php
│       ├── Dockerfile-php
│       └── php.ini
├── data
│   ├── mysql
│   └── redis
├── docker-compose.yml
├── dyde.env
├── log
│   ├── mysql
│   └── nginx
└── README.md
```

Installed PHP extensions
------------------------

```
[PHP Modules]
bz2
Core
ctype
curl
date
dom
exif
fileinfo
filter
ftp
gd
hash
iconv
imagick
intl
json
libxml
mbstring
mcrypt
mongodb
mysqli
mysqlnd
openssl
pcre
PDO
pdo_mysql
pdo_pgsql
pdo_sqlite
pgsql
Phar
posix
readline
redis
Reflection
session
SimpleXML
soap
SPL
sqlite3
standard
tokenizer
xml
xmlreader
xmlwriter
Zend OPcache
zip
zlib

[Zend Modules]
Zend OPcache
```

Customization
-------------

