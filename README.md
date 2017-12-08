# Docker Web Server
A lightweight docker service designed with the bare minimum required to run a PHP website. The service encapsulates:
* Nginx
* PHP 7.1 (FPM)
* Redis
* MariaDB

The PHP fpm container also comes preinstalled with:
* Git
* Composer
* Node (+ npm)
* PHPUnit

## Set up
1. Place/clone your source code into the **volumes/www** directory
2. Copy **.env.example** and name it **.env**
3. Put in your new desired database connection details into **.env**
4. Run ``docker-compose up -d`` to start the service

### Database connection
Instead of the conventional `127.0.0.1` or `localhost` as a database host setting, you should instead use `database`.

### Redis connection
Likewise, redis should connect to `redis` and not `127.0.0.1`.