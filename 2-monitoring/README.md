# Prometheus stack
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install prom-stack prometheus-community/kube-prometheus-stack -n monitoring --create-namespace
```