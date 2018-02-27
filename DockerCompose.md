
### Ideal for local development and test

docker-compose --help

docker-compose.yml is the default filename but any filename can be used once its a .yml file e.g 

docker-compose -f <yaml filename>
  
**Sample Docker Compose File**

version: '3.1'  # if no version is specificed then v1 is assumed. Recommend v2 minimum

services:  # containers. same as docker run
  servicename: # a friendly name. this is also DNS name inside network
    image: # Optional if you use build:
    command: # Optional, replace the default CMD specified by the image
    environment: # Optional, same as -e in docker run
    volumes: # Optional, same as -v in docker run
  servicename2:

volumes: # Optional, same as docker volume create

networks: # Optional, same as docker network create

  

**Good Example Here Also https://github.com/dockersamples/example-voting-app/blob/master/docker-compose.yml**
