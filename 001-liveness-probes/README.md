# 001 — Kubernetes Liveness Probes

Companion configs for **"Your Pod Is Running. Your Service Is Dead."** ([watch](https://www.youtube.com/@augmentedops))

## What's here
- [`probes.yaml`](probes.yaml) — two deployments:
  - **payments-api**: liveness + readiness probes with the video's numbers (`3 × 10s = 30s` time-to-detect)
  - **java-app**: a slow starter protected by a `startupProbe` (60s boot budget)

## Try it
```
kubectl create namespace ops-bits
kubectl apply -n ops-bits -f probes.yaml
kubectl get pods -n ops-bits -w
```
The example images are placeholders — point them at any container that serves HTTP on 8080 (or `kubectl edit` the probe paths to match yours).

## The one rule
**Liveness probes check your process. Readiness probes handle the dependencies.**
A liveness probe that checks the database converts a database outage into a cluster-wide restart storm.
