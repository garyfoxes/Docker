**Create Pod**

kubectl create -f helloworld.yml (will create pod and assign to cluster)

Edit the data in docker-registry.yaml in JSON using the v1 API format then create the resource using the edited
data.

kubectl create -f docker-registry.yaml --edit --output-version=v1 -o json

Sample Yaml File

apiVersion: v1

kind: Pod

metadata:

  name: nodehelloworld.example.com
  
  labels:
  
    app: helloworld
    
spec:

  containers:
  
  - name: k8s-demo
  
    image: wardviaene/k8s-demo
    
    ports:
    
    - name: nodejs-port
    
      containerPort: 3000
      
      


