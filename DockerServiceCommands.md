
Use --help for list of commands

**Docker Service Is Used To Replace The Docker Run Command**


**Add Swarm**

docker swarm init (tokens and certificates are created)(First Node created is a manager)

docker node ls (list available nodes)

**Docker Service**

N.B* Service store containers

docker service create alpine ping 8.8.8.8 (Creates a service with the alpine image)

docker service ps serviceName (Information about the service)

docker service update serviceName --replicas 3  (Update the number of nodes with alpine to 3, if one of the containers goes down the service will recreate another container)



