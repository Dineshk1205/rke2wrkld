# platform-gitops

Fleet bundles for the ai-prod cluster (target: clusters labelled env=ai-prod).

| Bundle | Component | Version |
|---|---|---|
| longhorn | Longhorn distributed storage | 1.13.0 |
| metallb | MetalLB load balancer | 0.16.2 |
| metallb-config | IP address pool 172.16.40.50-172.16.40.69, L2 advertisement | - |
| gpu-operator | NVIDIA GPU Operator (pre-installed driver, DCGM ServiceMonitor) | v26.7.2 |
| monitoring-agent | Prometheus agent, node-exporter, kube-state-metrics; remote write to the management cluster | kube-prometheus-stack 93.4.0 |
| ai-ollama | Ollama on wrkldc04 (models llama3.2:3b, qwen2.5:7b, nomic-embed-text) | chart 1.95.0 |
| ai-vllm | vLLM OpenAI-compatible server on wrkldc05 (Qwen2.5-1.5B-Instruct), ServiceMonitor | v0.34.0 |
| ai-qdrant | Qdrant vector database for RAG | chart 1.20.2 |
| ai-open-webui | Open WebUI at http://ai.gpu.lab, connected to Ollama and vLLM, RAG with Qdrant and nomic-embed-text | chart 18.4.0 |

Credentials (remote write) are Kubernetes Secrets created on the cluster, not stored in this repository.
