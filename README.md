# SymfoDock (PHP7 - NGINX - MySQL - ELK - REDIS - RABBITMQ)

*This project is a fork of  [maxpou/docker-symfony](https://github.com/maxpou/docker-symfony) Many thanks *

## Installation

* Clone the project
```bash
$ git clone git@github.com:prodriguezval/symfodock.git
```
* review the docker-compose.example file, change the parameter that you want (passwords, directory names, etc)
* create the docker-compose file
```bash
$ cp docker-compose.example docker-compose.yml
```
* Update your host file
```bash
sudo echo "localhost symfony.dev" >> /etc/hosts
```
* Build the containers
```bash
docker-compose up -d
```

## Usage

* Symfony app: visit symfony.dev
* Symfony dev mode: visit symfony.dev/app_dev.php
* Logs (Kibana): symfony.dev:81
* Logs (files location): logs/nginx and logs/symfony

## Tips
* The php container includes Node.js, Bower and gulp 
```bash
docker exec -it symfodock_php_1 bash
npm -v
bower -v
gulp -v
```

Enjoy.