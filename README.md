# jackindabox

A local Kubernetes platform built with OpenTofu, one small step at a time.

## What it does

Creates a single-node kind cluster running Kubernetes 1.36.1 and installs Argo CD on it. The node image is pinned by digest. The cluster is managed by the `tehcyx/kind` provider 0.11.0, and Argo CD is installed from the `argo-cd` Helm chart 10.9.2 (Argo CD v3.5.3) with the `hashicorp/helm` provider 3.3.0. The config is in `infra/envs/local/main.tf`.

## Requirements

| Tool | Version |
|------|---------|
| Docker | 29.2.1 |
| OpenTofu | 1.12.6 |
| kubectl | 1.33.1 |

## Usage

```sh
cd infra/envs/local
tofu init
tofu apply
kubectl get nodes
kubectl get pods -n argocd
```

Remove the cluster with:

```sh
tofu destroy
```
