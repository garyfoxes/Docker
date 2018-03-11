**Can Use Composr Files For Deploying**

docker stack deploy -c composeFileName voteapp

docker stack services stackName

https://hub.docker.com/r/dockersamples/visualizer/ (for viewing stack)

Sample setup

visualizer:
    image: dockersamples/visualizer
    ports:
      - "8080:8080"
    stop_grace_period: 1m30s
    volumes:
      - "/var/run/docker.sock:/var/run/docker.sock"
    deploy:
      placement:
        constraints: [node.role == manager]
        
  
  

