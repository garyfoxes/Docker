kubectl run hello-minikube --image=gcr.io/google_containers/echoserver:1.4 --port=8080 (deploys container to cluster)

kubectl expose deployment hello-minikube --type=NodePort --port=8080 --name=my-service(exposes container on host machine)

minikube stop (Stops cluster)

minikube service hello-minikube --url (gets url of container)

export NODE_PORT=$(kubectl get services/kubernetes-bootcamp -o go-template='{{(index .spec.ports 0).nodePort}}')
echo NODE_PORT=$NODE_PORT

kubectl describe deployments hello-minikube (get info on container)

kubectl delete deployments --all (delete all deploymenets)

http://192.168.99.100:30000/ (dashboard)

https://medium.com/google-cloud/kubernetes-101-pods-nodes-containers-and-clusters-c1509e409e16 Structure of pods v clusters



