``` bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install prometheus prometheus-community/kube-prometheus-stack
kubectl port-forward prometheus-prometheus-kube-prometheus-prometheus-0 9090:9090 -n default
kubectl port-forward alertmanager-prometheus-kube-prometheus-alertmanager-0 9093:9093 -n default
kubectl port-forward deployment/prometheus-grafana 3000
kubectl expose deployment prometheus-grafana --port=3000 --target-port=3000 --type=LoadBalancer
kubectl get svc
kubectl get pods -o wide
kubectl apply -f deploy-with-error.yaml

####### MÉTRICAS PARA O GRAFANA

# lição de casa: kube_pod_status_reason{namespace="$namespace",reason="Evicted"}
# kube_pod_status_phase{namespace="$namespace",phase="Pending"}

####### SENHA GRAFANA

# usuário: admin
# senha: prom-operator

```

```
### infinite calls

apiVersion: apps/v1
kind: Deployment
metadata:
  name: infinite-calls
  labels:
    app: infinite-calls
spec:
  replicas: 1
  selector:
    matchLabels:
      app: infinite-calls
  template:
    metadata:
      name: infinite-calls
      labels:
        app: infinite-calls
    spec:
      containers:
      - name: infinite-calls
        image: busybox
        command:
        - /bin/sh
        - -c
        - "while true; do wget -q -O- 10.0.2.233:8080; done"


```


```
####### Habilitar Prometheus pelo GitLab: mencionamos no curso, porém já está DEPRECATED
####### Se você quiser tentar, a lição de casa está em:  
####### https://docs.gitlab.com/ee/user/clusters/applications.html#install-prometheus-using-gitlab-cicd

prometheus:
  installed: true

```