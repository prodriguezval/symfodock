# SymfoDock (PHP7 - NGINX - MySQL - ELK - REDIS - RABBITMQ)

* **This project begun as a fork of  [maxpou/docker-symfony](https://github.com/maxpou/docker-symfony) Many thanks**
* **This is currently inspired in  [LaraDock/laradock](https://github.com/LaraDock/laradock) Many thanks**


## Installation

* Clone the project
```bash
$ git clone git@github.com:prodriguezval/symfodock.git
```

The concept of this project is deliver with docker from dev to prod, to achieve that use the docker's .env file to configure some variables for each different environment

```bash
$ cp .env.example .env
```
* Review the .env file and change the values as you need

* Update your host file
```bash
sudo echo "localhost symfony.dev" >> /etc/hosts
```
* Build the containers
You can start only the services that you need (MySQL, NGINX, PHP-FPM), with this line: 
```bash
docker-compose up -d nginx mysql
```

This is fine to begin, but if you need any other service like log reading, or redis  look for the alias of the service in the docker-compose.yml and add it to the command like this: 

```bash
docker-compose up -d nginx mysql elk redis
```

## Usage

* Symfony app: visit symfony.dev
* Symfony dev mode: visit symfony.dev/app_dev.php
* Logs (Kibana): symfony.dev:81
* Logs (files location): logs/nginx and logs/symfony


Any contribution will be welcome :)
 
Enjoy.
