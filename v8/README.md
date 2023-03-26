# EKS v8

## This project is under development.

#### Step 1 — Install the ECK operator CRDs

```shell
helm repo add elastic https://helm.elastic.co
helm repo update

helm install elastic-operator elastic/eck-operator -n logging --create-namespace
```

#### Step 2 — Create priority classes (Optional)

```shell
kubectl apply -f elastic-priority-classes.yaml
```

#### Step 3 — Create the Elasticsearch cluster

```shell
kubectl apply -f elasticsearch-cluster.yaml -n logging
```

#### Step 4 — Create a Kibana instance

```shell
kubectl apply -f kibana-instance.yaml -n logging
```

#### Step 5 — Install Filebeat

```shell
kubectl apply -f filebeat-kubernetes.yaml
```

#### Resources

- Run Elastic Stack on Kubernetes - https://medium.com/@KushanJanith/run-elastic-stack-on-kubernetes-29e295cd6531
- Kubernetes Package - https://artifacthub.io/
- NGINX Ingress Controller - https://kubernetes.github.io/ingress-nginx/deploy/
- ECK - https://www.elastic.co/guide/en/cloud-on-k8s/2.6/k8s-deploy-eck.html