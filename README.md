# K8S Benchmark testing Stack 

This repo is meant to be a GitOps repository to install a stack composed by:

- Prometheus
- Grafana
- MySql
- Kong

# Create the cluster

k3d cluster create test \
  --api-port 6550 \
  -p "8081:80@loadbalancer" \
  -p "8443:443@loadbalancer" \
  --agents 2 

# Install Argo

helm install argocd helm/argocd

## ArgoCD Self managed

kubectl apply -f app-of-apps.yaml