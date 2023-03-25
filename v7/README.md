# EKS

#### Step 1 — Install Filebeat

```shell
cd filebeat/
helm install filebeat . -n logging --create-namespace
```

#### Step 2 — Install Logstash

```shell
cd logstash/
helm install logstash . -n logging --create-namespace
```

#### Step 3 — Install Elasticsearch

```shell
cd elasticsearch/
helm install elasticsearch . -n logging --create-namespace
```

#### Step 4 — Install Kibana

```shell
cd kibana/
helm install kibana . -n logging --create-namespace
```

#### Step 5 — Run Kibana

```shell
kubectl port-forward service/kibana-kibana 8080:5601 -n logging
```


#### Resources

- NGINX Ingress Controller - https://kubernetes.github.io/ingress-nginx/
- Kubernetes packages - https://artifacthub.io/
- YT - https://www.youtube.com/watch?v=SU--XMhbWoY&t=634s