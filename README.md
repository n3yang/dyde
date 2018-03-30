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
2. Prepare enviroment

* Copy dyde.env to .env
* Edit .evn file, change some variables you want. (Optional)

3. Run
Rebuid PHP image, install extensions and composer
```bash
docker-compose up -d
```
Create yii2 project
```bash
docker run -it --rm dyde_php_1 composer create-project --prefer-dist yiisoft/yii2-app-basic app
```
The "dyde_php_1" is PHP container's name in your project.

Visit http://localhost:8000/ (default nginx http port)

Tree of directiory
------------------


Installed PHP extensions
------------------------


Customization
-------------

