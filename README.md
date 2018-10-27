# DEMP Stack

The world has changed, The time using XAMPP, EasyPHP, WAMP or anything else has long gone and the age of Docker has brought us the light of isolation.

DEMP stands for Docker Nginx MySQL and PHP.  
This is a simple docker-compose project proposed for development.  

The main benefit is you don't need to change anything in your workstation and it's highly portable, all you need is **Docker** installed.

## Requirement:
All you need is, to install [docker](https://docs.docker.com/install) and then clone the project and run the following command:  
``docker-compose up -d``  
The first time may take some minutes for containers to start.

## What this Stack Offer:
* PHP 7.1 with most used modules and composer installed(check Dockerfile for more info).
* MariaDB (Latest Version)
* Nginx (Latest version)

You can find `php.ini` in `./docker/php/php.ini`  
If you need to change anything remember you need to restart the container for the change to take effect.   

Nginx configuration can be found in `./docker/nginx/`. Also, nginx logs goes to `logs` directory inside `nginx` directory.

Your project source must go under `src` directory. Nginx default check for `index.php` in `src/public` to comply with modern frameworks like Laravel so if it's not your case, you may change nginx configuration.

## Configuration
Check the `.env` file. You can change image version if you want and also modify services exposed port.

### Note:
If you are on Windows and you experience a problem with MariaDB please kindly remove the related volume in `docker-compose.yml` and restart containers, Also remember with these changes you will loose your data once the container gets deleted.
