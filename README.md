# Guacamole-Docker-Compose
Docker compose YAML file to setup Guacamole from official images

## Notes about this docker-compose file
* Please change the password. It is intended to use the same password in all places that have "changeme"
* Start order dependencies along with health checks were added to make sure the MySQL database was up and running prior to Guacamole starting and attempting to connect
* MySQL volume was made external on line 23
    * /opt/mysql_data:/var/lib/mysql 
    * This will store the mysql database in the /opt/mysql_data directory on the host machine and allow the docker containers to be destroyed without losing the MySQL database
    * To keep the data internal to the docker container simply change line 23 to the following:
        * /var/lib/mysql
* All docker containers will restart automatically unless manually stopped