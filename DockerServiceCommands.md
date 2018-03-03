
Use --help for list of commands


https://get.docker.com/ (If setting up docker on machine can install via here)

**Docker Service Is Used To Replace The Docker Run Command**


**Add Swarm**

Service will deploy images/containers to nodes

https://labs.play-with-docker.com (for creating swarms and nodes,sessions only last 4 hrs)

docker swarm init (tokens and certificates are created)(First Node created is a manager and is also the leader)

docker node ls (list available nodes)

docker swarm join --token SWMTKN-1-402j4pqkzcwgirm1finst6ozhm7rsw135ex4ixo0fz25zq5xv7-d3kb9u1yip75btbjmff2ke862 192.168.0.53:2377 

(Above Will Add node to the swarm as a worker, this cannot run swarm commands as it is a worker and has not got priviliged commands)

docker node update node2 --role manager (Update priviliges to node worker, do docker node ls to get list of nodes)

docker swarm join --token SWMTKN-1-402j4pqkzcwgirm1finst6ozhm7rsw135ex4ixo0fz25zq5xv7-2e8i98k40wj1wob800nd549i7 192.168.0.53:2377 (Add as a manager, token is different to the token when adding a worker)

docker service create --replicas 3 alpine ping 8.8.8.8 (Creates a service with the alpine image, this will add the alpine container to each node) 

 docker network create --driver overlay mydrupal (OVERLAY IS USED IN SWARMS FOR CONNECTING WITH NODES)
 
 docker service create --name mypsql --network mydrupal -e POSTGRES_PASSWORD=password postgres
 
 docker service create --name drupal --network mydrupal -p 80:80 drupal (when setting up drupal the db name is the postgress service name)

**Docker Service**

N.B* Service store containers

docker service create --name serviceName --replicas 3 alpine ping 8.8.8.8 (Creates a service with the alpine image)

docker service ps serviceName (Information about the service)

docker service update serviceName --replicas 4  (Update the number of containers with alpine to 3, if one of the containers goes down the service will recreate another container)

docker service rm serviceName (Will remove service and all containers within that service)



