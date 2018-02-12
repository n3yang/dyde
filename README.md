# DYDE (Docker Yii2 Development Environment)
Easy way for creating yii2 framework development environment with docker compose.

About Yii2 framework
* [Yii2 framework](https://www.github.com/yiisoft/yii2)

Images to used:  
* [Nginx](https://hub.docker.com/_/nginx/)
* [PHP](https://hub.docker.com/_/php/)
* [MariaDB(Mysql)](https://hub.docker.com/_/mariadb/)
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
2. Edit enviroment (Optinal)

Edit dyde.evn file, change some variables you want.

3. Run
```bash
docker-compose up -d
```
Visit http://localhost:8000/

Tree of directiory
------------------



Customization
-------------

