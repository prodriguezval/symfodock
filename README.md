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
docker-compose up
```
