docker info
docker version

docker container run --publish 80:80 --detach --name webserver nginx (Starts nginx server opens port 80 on your host and routes it to port 80 on your container)
docker container run --publish 80:80 nginx (Same as above but shows requests and logs)
docker container run -d -p 3306:3306 --name db -e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql 

docker container ls -a
docker container stop <containerName>/ID>
docker container rm -f <conatinerName/ID> <containerName/ID>

docker rm -f $(docker ps -a -q)  (Stops All Containers)
docker kill $(docker ps -q)       (Removes All Containers)
docker rmi $(docker images -q)    (Removes All Images)

Run Shell Inside Container
docker container exec -it db bash

Get Port And I.P Of Container
docker container port nginx
docker container inspect --format '{{.NetworkSettings.IPAddress}}' nginx
