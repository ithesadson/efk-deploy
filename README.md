# efk-deploy

DEPLOY Elasticsearch, Filebeat & Kibana

helm repo add elastic https://helm.elastic.co
helm repo update

helm install elasticsearch elastic/elasticsearch \
  --namespace logging \
  -f elasticsearch-values.yaml \
  --create-namespace

helm install filebeat elastic/filebeat \
  --namespace logging \
  -f filebeat-values.yaml


helm install kibana elastic/kibana \
  --namespace logging \
  -f kibana-values.yaml
