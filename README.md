# K8S Benchmark testing Stack 

This repo is meant to be a GitOps repository to install a stack composed by:

- Prometheus
- Grafana
- MySql
- Kong

# Create the cluster

k3d cluster create --api-port 6550 -p "8081:80@loadbalancer" --agents 2