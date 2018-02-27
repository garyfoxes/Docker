
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

**Example 2 Docker Compose File**

version: "3"
services:
  web:
    # replace username/repo:tag with your name and image details
    image: username/repo:tag
    deploy:
      replicas: 5
      resources:
        limits:
          cpus: "0.1"
          memory: 50M
      restart_policy:
        condition: on-failure
    ports:
      - "80:80"
    networks:
      - webnet
networks:
  webnet:
This docker-compose.yml file tells Docker to do the following:

Pull the image we uploaded in step 2 from the registry.

Run 5 instances of that image as a service called web, limiting each one to use, at most, 10% of the CPU (across all cores), and 50MB of RAM.

Immediately restart containers if one fails.

Map port 80 on the host to web’s port 80.

Instruct web’s containers to share port 80 via a load-balanced network called webnet. (Internally, the containers themselves publish to web’s port 80 at an ephemeral port.)

Define the webnet network with the default settings (which is a load-balanced overlay network).

**Good Example Here Also https://github.com/dockersamples/example-voting-app/blob/master/docker-compose.yml**
