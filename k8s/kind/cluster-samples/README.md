# My first cluster with kind: single node 

kind create cluster --name [cluster-name]

Kind get clusters # look all clusters 

kind delete clusters [name]

kind get nodes

# Get kubernetes context: 

kubectl cluster-info --context [cluster-name]

# Kind create cluster wiht config file: 
 # use the deployment files in cluster-samples folder to understand how you can deploy different types of clusters.
 
kind create cluster --name [cluster-name] --config [configuration-file.yaml]  



# Kubernetes versions to use with kind: 

https://github.com/kubernetes-sigs/kind/releases

