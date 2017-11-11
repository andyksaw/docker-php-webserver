# Docker Web Server
A lightweight docker service designed with the bare minimum required to run a PHP website. The service encapsulates:
* Nginx
* PHP 7.1 (FPM)
* Redis
* MariaDB

The PHP fpm container also comes preinstalled with:
* Git
* Composer
* Node/NPM

## Set up
1. Place/clone your source code into the **storage/www** directory
2. Copy **.env.example** and name it **.env**
3. Put in your new desired database connection details into **.env**
4. Run ``docker-compose up -d`` to start the service

### Database connection
Instead of the conventional `127.0.0.1` or `localhost` as a database host setting, you should instead use `database`.

### Redis connection
Likewise, redis should connect to `redis` and not `127.0.0.1`.

## Recommended workflow
This service can act as both a local development environment or a production environment.

For dev use, edit your source code as per usual from the **storage/www** directory. 
1. Run ``docker exec -it <php-fpm container id> sh`` to jump into the PHP container (Use ``docker ps`` to find the container's ID).
2. Run your desired cli commands: ``compose install`` or ``npm install`` or ``php artisan migrate``, etc.