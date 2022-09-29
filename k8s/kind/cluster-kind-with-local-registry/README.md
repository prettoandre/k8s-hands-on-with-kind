# create a cluster kind and local docker registry
    # run bash script:
    ./create-cluster-with-registry-local.sh

# How create your docker image and push to local registry: 

docker pull nginx:latest

docker tag nginx:latest localhost:5000/my-nginx-app:1.0
docker push localhost:5000/my-nginx-app:1.0

docker tag nginx:latest localhost:5000/my-nginx-app:2.0
docker push localhost:5000/my-nginx-app:2.0

curl http://localhost:5000/v2/_catalog | jq .

# create a deployment
kubectl apply -f deployment.yaml

# when make changes to update deployment
kubectl replace -f deployment.yaml --force

# how expose service
kubectl expose deployment nginx-deployment --type=NodePort --name=thepumbles-service

kubectl expose deployment nginx-deployment --type=LoadBalancer --name=lb-thepumblers-service

kubectl get services 
kubectl describe services 

kubectl get pod pod-name --template='{{(index (index .spec.containers 0).ports 0).containerPort}}{{"\n"}}'

kubectl port-forward deployment-name 8080:80

or 

kubectl port-forward deployment/nginx-deployment 8080:80

or 

kubectl port-forward service/lb-thepumblers-service 8080:80


# clean service 
kubectl delete services 

# kubectl utils

kubectl get deployments

kubectl describe deployments

kubectl get replicasets
kubectl describe replicasets

kubectl get pods -o wide --watch  

kubectl get nodes --show-labels


# clean all docker
docker stop $(docker ps -aq)
docker rm -f $(docker ps -a -q)
docker volume rm $(docker volume ls -q)



