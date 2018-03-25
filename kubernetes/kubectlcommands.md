kubectl run hello-minikube --image=gcr.io/google_containers/echoserver:1.4 --port=8080 (deploys container to cluster)

kubectl expose deployment hello-minikube --type=NodePort (exposes container on host machine)

minikube service hello-minikube --url (gets url of container)

ubectl describe deployments hello-minikube (get info on container)
