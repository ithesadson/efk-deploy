
# EFK Deploy Guide

Deploy **Elasticsearch**, **Filebeat**, and **Kibana** using Helm charts in a Kubernetes cluster.

---

## Step 1: Add Elastic Helm Repository

```bash
helm repo add elastic https://helm.elastic.co
helm repo update
```

---

## Step 2: Deploy Elasticsearch

```bash
helm install elasticsearch elastic/elasticsearch \
  --namespace logging \
  -f elasticsearch-values.yaml \
  --create-namespace
```

---

## Step 3: Deploy Filebeat

```bash
helm install filebeat elastic/filebeat \
  --namespace logging \
  -f filebeat-values.yaml
```

---

## Step 4: Deploy Kibana

```bash
helm install kibana elastic/kibana \
  --namespace logging \
  -f kibana-values.yaml
```

---

> ✅ Make sure the `elasticsearch-values.yaml`, `filebeat-values.yaml`, and `kibana-values.yaml` files are properly configured before running the commands.
