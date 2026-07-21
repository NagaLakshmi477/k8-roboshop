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
kubectl apply -f manifest.yaml
kubectl get pods
alias ka="kubectl apply -f manifest.yaml"
alias kp="kubectl get pods"
kp -n roboshop --> beacuse we mentioned namespace as roboshop in mainfest file
to avios this everytime giving " -n roboshop" we need to install tools
kubens:
-------
sudo git clone https://github.com/ahmetb/kubectx.git /opt/kubectx
sudo ln -s /opt/kubectx/kubens /usr/local/bin/kubens
k9s:
----
curl -sS https://webinstall.dev/k9s | bash
 
shift+ : --> you can type
esc
cl+c

- we need to provide the env variable to catalogue we can ConfigMap
- we need to refer the config map that we have created using envForm
- to check logs we installed some tools using docker file
docker build -t lakshmi1092/debug:v1 .
docker push  lakshmi1092/debug:v1
--run manifest file for debug

In frontend we use 80 bu some ports are resrved ink8s so we need to change te ports based onthe rangs
