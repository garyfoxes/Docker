**KUBECTL**

kubernetes command line tool

 https://storage.googleapis.com/kubernetes-release/release/v1.6.1/bin/darwin/amd64/kubectl (mac)
 
 curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/darwin/amd64/kubectl (latest stable version)
 
 chmod +x ./kubectl
 
 sudo mv ./kubectl /usr/local/bin/kubectl
 
 https://storage.googleapis.com/kubernetes-release/release/v1.6.1/bin/linux/amd64/kubectl (linux)
 
 **Minikube**
 
 Installs kubernetes locally
 
 brew cask install minikube (mac)
 
 curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/ (linux)
 
 minikube start
 
 cd ~/.kube/ && pcat config
 
 **List Of Helpful Resources Here**
 
 https://www.udemy.com/learn-devops-the-complete-kubernetes-course/learn/v4/t/lecture/6018348?start=0
