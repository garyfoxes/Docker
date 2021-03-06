
https://docs.docker.com/compose/compose-file/ (very good documentation here)

### Ideal for local development and test

docker-compose --help

docker-compose.yml is the default filename but any filename can be used once its a .yml file e.g 

docker-compose -f <yaml filename>
 
docker-compose up  -d (run compose file in backgroud)

docker-compose down (remove containers)

docker-compose logs (inspect logs)

docker-compose run run_tests protractor conf.js --params.browsers="chrome_regression" --specs="ui_tests/engine/desktop/specs/e2e_spec/*.js" --baseUrl="https://www.holidayautos.com" --params.environment="staging" --params.buildNumber="5.46.1--1712" --seleniumAddress="http://172.20.0.2:4444/wd/hub" 

  
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

**Also Here For Selenium Grid https://github.com/elgalu/docker-selenium/blob/master/docker-compose-scales.yml**
