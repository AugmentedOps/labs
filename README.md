# Ops Bits — companion configs

Working configuration files for the **[AugmentedOps](https://www.youtube.com/@augmentedops)** Ops Bits series — single-concept infrastructure explainers. Every episode's YAML lives here, tested and copy-paste ready.

> Modern ops, augmented by AI. · [augmentedops.io](https://augmentedops.io)

| # | Episode | Configs |
|---|---------|---------|
| 001 | Your Pod Is Running. Your Service Is Dead. (Kubernetes Liveness Probes) | [001-liveness-probes/](001-liveness-probes/) |

## Using these configs

Each directory is self-contained. Manifests are plain Kubernetes YAML — apply into a test namespace:

```
kubectl create namespace ops-bits
kubectl apply -n ops-bits -f 001-liveness-probes/probes.yaml
```

Nothing here is production-ready as-is: values are tuned to demonstrate the episode's concepts. Read the comments, then adapt to your workloads.
