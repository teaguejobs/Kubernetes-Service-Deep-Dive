## KUBERNETES SERVICE DEEP DIVE ##

# Step 1 #

- Install minikube on ubuntu or Ec2 instance 

[minikube installation](https://minikube.sigs.k8s.io/docs/start/)

- On the repo we will find all th files for a sample python application
- Firstly lets build our image `docker build -t teaguejobs/sample-python-app-demo:v1 .`
- Create a deployment.yml file on the root of our repo
- copy the name of the newly created image and replace on the image section on the deployment file
- create and apply the newly created deployment.yml 
- `kubectl create -f deployment.yml`
- `kubectl apply -f deployment.yml`
- In order to access our clusters we need to create a service.yml file
- `kubectl create -f service.yml`
- make sure the selector on the deployment and services matches. Always copy from the template
- Edit the port type to NodePort or LoadBalancer
- change target port to 8000 as specified on your dockerfile 
- In order to access your application on NodePort mode type `minikube ip`
- `curl -L minikube i.p:30007`
- In order to access your application fromm a load balancer
- `kubectl edit svc.yml`
- change porttype to LoadBalancer
- access Application on local.ip:30007

- We can check how traffic flows using kubeshark tool

Install kubeshark 

[kubeshark](https://docs.kubeshark.co/en/install)




