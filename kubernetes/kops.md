brew update && brew install kops (Install)

brew doctor

brew install python (going to use python-pip for using aws command line)

sudo easy_install pip

sudo -H pip install --ignore-installed awscli (Install command line for aws)

If there are permission issues run:

sudo mkdir /usr/local/Frameworks

sudo chown $(whoami):admin /usr/local/Frameworks

**Go To AWS Setup Now And Then Continue**

kops create cluster --name=kubernetes.newtech.academy.k8s.local --state=s3://kops-state-1985 --zones=eu-west-1a --node-count=2 --node-size=t2.micro --master-size=t2.micro (Creates cluster configuration with 3 instances)

This actually uses the ssh key at the default location ~/.ssh/id_rsa_pub, pass the --ssh-public-key flag to the loaction of the public key you want to use.

name - end cluster name with k8s.local if skipping DNS setup
state - s3 name you setup
zones - can see available zones in the ec2 home normally end with a,b or c
node-count- number of nodes
node-size - Instance size

**Edit cluster configuration**

kops edit cluster kubernetes.newtech.academy.k8s.local --state=s3://kops-state-1985

**Run Cluster**

kops update cluster kubernetes.newtech.academy.k8s.local --yes --state=s3://kops-state-1985

Config wrote to ~/.kube/config (In this config is the username and password to login to)


**Extra Commands**

validate cluster: kops validate cluster

list nodes: kubectl get nodes --show-labels

ssh to the master: ssh -i ~/.ssh/id_rsa admin@api.kubernetes.newtech.academy.k8s.local


**Run Container In AWS**

kubectl run hello-minikube --image=gcr.io/google_containers/echoserver:1.4 --port=8080

kubectl expose deployment hello-minikube --port=8080 --type="NodePort"

kubectl get service (This will expose the port to access)


**Open Firewall In AWS**

Go To VPC -> Security Groups -> Master Node -> Inbound Rules -> Add

Add 0.0.0.0/0 to allow everyone access 

Do for nodes as well.






