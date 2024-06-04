# kubernetes1

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
