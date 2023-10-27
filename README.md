# minikube-setup

Setup minikube at your local and explore creating namespaces

Install Docker:

Minikube requires Docker. Install Docker on  EC2 instance

sudo yum update -y

sudo amazon-linux-extras install docker -y

sudo service docker start

sudo usermod -aG docker $USER

Install kubectl:

Install kubectl, the Kubernetes command-line tool

sudo curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

sudo chmod +x kubectl

sudo mv kubectl /usr/local/bin/


Install Minikube

curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

chmod +x minikube

sudo mv minikube /usr/local/bin/


minikube start --kubernetes-version=1.21.0

Explore Namespace Creation

kubectl create namespace my-namespace

kubectl get namespaces

kubectl get pods -n my-namespace

Deploy Resources

kubectl create deployment nginx-deployment --image=nginx -n my-namespace

Access Minikube Services

minikube service <service-name> -n my-namespace





