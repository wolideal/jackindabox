# jackindabox

A local Kubernetes platform built with OpenTofu, one small step at a time.

## What it does

Creates a single-node kind cluster running Kubernetes 1.36.1. The node image is pinned by digest and the cluster is managed by the `tehcyx/kind` provider 0.11.0. The config is in `infra/envs/local/main.tf`.

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
```

Remove the cluster with:

```sh
tofu destroy
```
