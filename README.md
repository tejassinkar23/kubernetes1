# kubernetes1

aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 654654231724.dkr.ecr.ap-south-1.amazonaws.com

access key  :  AKIAZQ3DO2SWJQZBIUNN
secret key : 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
aws act id : 654654231724

docker tag my-flask-app:latest 654654231724.dkr.ecr.ap-south-1.amazonaws.com/my_monitoring_app_image:latest


docker push 654654231724.dkr.ecr.ap-south-1.amazonaws.com/my_monitoring_app_image:latest

TASKS:
go through AWS docs

deploy this project on locally after that try on EKS

get info about pulumi 
helmchart

go through networking conecpts


  mkdir -p $HOME/.kube
  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
  sudo chown $(id -u):$(id -g) $HOME/.kube/config

*K3S*
installed K3S from official documentation. 
  command used - curl -sfL https://get.k3s.io | sh -

Exported the kubeconfig 
  command used - export KUBECONFIG=/etc/rancher/k3s/k3s.yaml

Deployed a flask application from a yaml file (deployment.yaml) 
  command used - kubectl apply -f deployment.yaml 

Created a service for the flask application deployment. deployed the service from yaml file. 
  command used - kubectl apply -f flask-service.yaml

Configured port forwarding for the deployment and service 
  command used - kubectl port-forward deployment/flask-app 5000:5000

accessed the application from the IP of the pod's node.
  command used (to get the IP of Node) - kubectl get pods -n default -o wide
