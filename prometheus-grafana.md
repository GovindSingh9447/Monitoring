#############################Install prometheus##################################

git clone https://github.com/techiescamp/kubernetes-prometheus
kubectl create namespace monitoring
kubectl create -f clusterRole.yaml
kubectl create -f config-map.yaml
kubectl create  -f prometheus-deployment.yaml 
kubectl create -f prometheus-service.yaml --namespace=monitoring



#############################install kube state metrics###########################
git clone https://github.com/devopscube/kube-state-metrics-configs.git
kubectl apply -f kube-state-metrics-configs/


##############################install alert manager##############################

git clone https://github.com/bibinwilson/kubernetes-alert-manager.git
kubectl create -f AlertManagerConfigmap.yaml
kubectl create -f AlertTemplateConfigMap.yaml
kubectl create -f Deployment.yaml
kubectl create -f Service.yaml

##########################install grafana ####################################
git clone https://github.com/bibinwilson/kubernetes-grafana.git
kubectl create -f grafana-datasource-config.yaml
kubectl create -f deployment.yaml
kubectl create -f service.yaml

###########################node exporter###################################
git clone https://github.com/bibinwilson/kubernetes-node-exporter
kubectl create -f daemonset.yaml
kubectl create -f service.yaml
