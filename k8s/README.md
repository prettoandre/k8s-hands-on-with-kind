# tools and documentation

kubectl - https://kubernetes.io/docs/tasks/tools/

Helm - https://helm.sh/docs/intro/install/

kind is a tool for running local Kubernetes clusters using Docker container “nodes”.
kind was primarily designed for testing Kubernetes itself, but may be used for local development or CI. - https://kind.sigs.k8s.io/docs/user/quick-start/ 

K9s is a terminal based UI to interact with your Kubernetes clusters. The aim of this project is to make it easier to navigate, observe and manage your deployed applications in the wild. K9s continually watches Kubernetes for changes and offers subsequent commands to interact with your observed resources. - https://kind.sigs.k8s.io/docs/user/quick-start/


Plugins to use with kubectl - https://kubernetes.io/docs/tasks/extend-kubectl/kubectl-plugins/

Plugins repo - https://krew.sigs.k8s.io/plugins/


# Terminal with asteroids 

ZSH - https://ohmyz.sh/

Theme ZSH - https://github.com/romkatv/powerlevel10k


# kubectl cheat sheet 

# Get commands with basic output
kubectl get services                          # List all services in the namespace
kubectl get pods --all-namespaces             # List all pods in all namespaces
kubectl get pods -o wide                      # List all pods in the current namespace, with more details
kubectl get deployment my-dep                 # List a particular deployment
kubectl get pods                              # List all pods in the namespace
kubectl get pod my-pod -o yaml                # Get a pod's YAML

# Describe commands with verbose output
kubectl describe nodes my-node
kubectl describe pods my-pod

# List Services Sorted by Name
kubectl get services --sort-by=.metadata.name

# List pods Sorted by Restart Count
kubectl get pods --sort-by='.status.containerStatuses[0].restartCount'

# List PersistentVolumes sorted by capacity
kubectl get pv --sort-by=.spec.capacity.storage

# Get the version label of all pods with label app=cassandra
kubectl get pods --selector=app=cassandra -o jsonpath='{.items[*].metadata.labels.version}'

# Retrieve the value of a key with dots, e.g. 'ca.crt'
kubectl get configmap myconfig -o jsonpath='{.data.ca\.crt}'
  
