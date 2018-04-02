**Used For Organizing Cluster Access And Which Cluster To Focus On**

https://kubernetes.io/docs/concepts/configuration/organize-cluster-access-kubeconfig/

By default, kubectl looks for a file named config in the $HOME/.kube directory.

kubectl config view (View Config)

kubectl config use-context contextName (**Important If Specifying Which Cluster To Use**)

kubectl config current-context (The current context that is been used)

