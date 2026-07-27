# AugmentedOps Labs

Working configuration files for the **[AugmentedOps](https://www.youtube.com/@augmentedops)** channel — real infrastructure, really broken, really fixed. Every episode's manifests live here, tested and copy-paste ready, so you can reproduce what you watched.

> Modern ops, augmented by AI. · [augmentedops.io](https://augmentedops.io)

| Lab | Topic | Configs |
|-----|-------|---------|
| 001 | Kubernetes liveness probes — why the kubelet kills healthy-looking pods | [001-liveness-probes/](001-liveness-probes/) |

## Using these labs

Each directory is self-contained. Manifests are plain Kubernetes YAML — apply into a test namespace:

```
kubectl create namespace labs
kubectl apply -n labs -f 001-liveness-probes/probes.yaml
```

Nothing here is production-ready as-is: values are deliberately tuned to demonstrate each episode's failure mode. Read the comments, then adapt to your workloads.
