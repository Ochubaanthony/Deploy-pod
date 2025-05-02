# Deploy-pod
Kubernetes deploy pod

Steps
Install  minikube
Install kubectl

This link is for documentation for Minikube
https://minikube.sigs.k8s.io/docs/start/?arch=%2Fmacos%2Fx86-64%2Fstable%2Fbinary+download


Process to install Minikube Run this on your command 

curl -LO https://github.com/kubernetes/minikube/releases/latest/download/minikube-darwin-amd64
sudo install minikube-darwin-amd64 /usr/local/bin/minikube

Make sure your docker engine is running  before you run the command below
minikube start

Install Kubectl process from the website


Start Docker engine to enable the Minikube start
minikube start
kubectl get nodes


Nano pod.yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
  
spec:
  containers:
    - name: nginx
      image: nginx:1.14.2
      ports:
        - containerPort: 80

Save the yaml file

Step
kubectl create -f pod.yaml 
kubectl get pods
kubectl get pods -o wide
minikube ssh
curl 10.244.0.8

Kubectl cheatsheet
https://kubernetes.io/pt-br/docs/reference/kubectl/cheatsheet/

Step
kubectl delete pod nginx
kubectl logs
kubectl apply -f pod.yaml

How to debug 
kubectl describe pod nginx
kubectl logs nginx
