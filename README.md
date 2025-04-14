# K8S Benchmark testing Stack 

This repo is meant to be a GitOps repository to install a stack composed by:

- Prometheus
- Grafana
- MySql
- Kong

# Create the cluster

k3d cluster create test --api-port 6550 -p "8081:80@loadbalancer" --agents 2


k3d cluster create test \
  --api-port 6550 \
  -p "8081:80@loadbalancer" \
  -p "8443:443@loadbalancer" \
  --agents 2 

k3d cluster create mycluster \
  --api-port 6550 \
  --servers 1 \
  --agents 1 \
  --network host

# Install Argo

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

