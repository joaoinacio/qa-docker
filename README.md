### Ezplatform QA dockers

This aims to improve the maintainability of environments and the overall experience as QA.

Using a volume shared between containers with an ezplatform or ezpublish(**WIP**)  installation changes to the installation are instantaneous. 

This way, reproducing and testing issues in different environments is easier and faster.

#### Requirements
[docker-compose](https://docs.docker.com/compose/install/)

Make you read all the documentation.

#### Instalation

 * Clone this repository
 * Install ezplatform/ezpublish in the same directory
 * In ezplatform `parameters.yml` the database_host change to 'db'

#### Usage
Run the command
``` sh
$ docker-compose up -d
```
Now your containers are up and ready to use.

The webserver is exposed in `port 80` if there is already a service using this port is should be changed:
``` yml
  web:
     ...
    ports:
      - "81:80"
```
#####Selecting Environments

To change the service configuration use the UNIX environment variables `DOCKER_WEB`, `DOCKER_PHP`, `DOCKER_DB` 

The default values are:

`web: apache_php56`
`php: php_fpm56`
`db: mysql`

Example:  Changing webserver to nginx
``` sh
$ export DOCKER_WEB=nginx
```

All the service definitions are in their respective `.yml` file in the services directory.

(**TODO**) Use environment variables to select the environments


####TO DO

 - [ ] ezpublish support
 - [x] improve enviroments selection
 - [ ] reduce apache process
 - [ ] database data persistance