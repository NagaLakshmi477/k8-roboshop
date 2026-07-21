# k8-roboshop
1. build the image  --> this part is done on docker
2. configure the image

now we need to run it as kubernates pods
1st we need to create
1. namespaces
kubectl apply -f 01-namespace.yaml
kubectl get ns ---> to check namespaces

mongodb 
--------
- pod is a subset of deployement
- If we create a deployement we will have an adavantage
    i.e : we can automaticcaly get the replica set. if pod delete it will automatically creates new one 
- 


