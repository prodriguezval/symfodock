# SymfoDock

#### A docker environmet to work with symfony without any pain

* **This project begun as a fork of  [maxpou/docker-symfony](https://github.com/maxpou/docker-symfony) Many thanks**
* **This is currently inspired in  [LaraDock/laradock](https://github.com/LaraDock/laradock) Many thanks**


## Installation

* Clone the project
```bash
$ git clone git@github.com:prodriguezval/symfodock.git
```

The concept of this project is deliver with docker from dev to prod, to achieve that use the docker's .env file to configure some variables for each different environment

```bash
$ cp .env.dist .env
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

### Integration with Symfony
To integrate SymfoDock with you existing or new symfony project, you must: 
1) Modify the docker .env file APP_DIR variable with your project folder name
```
#Common args
...
APP_DIR=my_project_folder_name
...
```
2) The folder structure must be like this: 
```
development (main folder)
    - symfodock (symfodock folder)
    - my_project_folder_name (your project folder)
```
3) Parameters configuration
open your parameters.yml and modify the configuration like this:

```
parameters:
    ...
    database_host: mysql      # like the docker-compose.yml alias
    ...
    database_user: user       # MYSQL_USER in param the docker-compose.yml
    database_password: secret # MYSQL_PASSWORD in param the docker-compose.yml
    ...
    redis_address: redis      # like the docker-compose.yml alias
```

## Usage

* Symfony app: visit symfony.dev
* Symfony dev mode: visit symfony.dev/app_dev.php
* Logs (Kibana): symfony.dev:81
* Logs (files location): logs/nginx and logs/symfony


Any contribution will be welcome :)
 
Enjoy.
