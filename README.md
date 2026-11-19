# platform-gitops

Fleet bundles for the ai-prod cluster (target: clusters labelled env=ai-prod).

| Bundle | Component | Version |
|---|---|---|
| longhorn | Longhorn distributed storage | 1.13.0 |
| metallb | MetalLB load balancer | 0.16.2 |
| metallb-config | IP address pool 172.16.40.50-172.16.40.69, L2 advertisement | - |
| gpu-operator | NVIDIA GPU Operator (pre-installed driver, DCGM ServiceMonitor) | v26.7.2 |
| monitoring-agent | Prometheus agent, node-exporter, kube-state-metrics; remote write to the management cluster | kube-prometheus-stack 93.4.0 |

The remote write credentials are a Kubernetes Secret (prom-remote-write) created on the cluster, not stored in this repository.
