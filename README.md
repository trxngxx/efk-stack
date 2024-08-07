# Hướng dẫn cấu hình EFK lên cụm Kubernetes #

## Dependencies ##
1. Kubernetes Cluster
2. Containerd or docker setup

## Deploy ##
1. Namespace and Elasticsearch, Kibana
```bash
git clone https://github.com/trxngxx/efk-stack.git
kubectl apply -f /elk-stack/common/.
kubectl apply -f /elk-stack//k8s-deployment/elasticsearch/.
kubectl apply -f /elk-stack//k8s-deployment/kibana/.
```
2. Fluentd
```bash
kubectl apply -f /elk-stack//k8s-deployment/fluentd-serviceaccount.yml
kubectl apply -f /elk-stack//k8s-deployment/fluentd-clusterrole.yml
kubectl apply -f /elk-stack//k8s-deployment/fluentd-clusterrolebinding.yml
kubectl apply -f /elk-stack//k8s-deployment/fluentd-configmap.yml
kubectl apply -f /elk-stack//k8s-deployment/fluentd.yml
```
## Checking ##
```bash
kubectl get all -n logging
```
