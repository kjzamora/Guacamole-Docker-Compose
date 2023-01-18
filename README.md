# Guacamole-Docker-Compose
Docker compose YAML file to setup Guacamole from official images

## Notes about this docker-compose file
1. Please change the password. It is intended to use the same password in all places that have "changeme"
2. Start order dependencies along with health checks were added to make sure the MySQL database was up and running prior to Guacamole starting and attempting to connect
3. MySQL volume was made external on line 23
    3.a. /opt/mysql_data:/var/lib/mysql 
    3.b. This will store the mysql database in the /opt/mysql_data directory on the host machine and allow the docker containers to be destroyed without losing the MySQL database
    3.c. To keep the data internal to the docker container simply change line 23 to the following:
        3.c.i. /var/lib/mysql
4. All docker containers will restart automatically unless manually stopped