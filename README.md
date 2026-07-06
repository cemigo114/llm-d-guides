# llm-d-guides

Field-tested deployment guides for serving large open models on
Kubernetes/OpenShift with vLLM. Configs, benchmark commands, and
measured numbers — including what didn't work and why.

## Guides

### [GLM 5.2 FP8 on H200](glm5.2-H200-guides/agentic-serving/README.md)

Three validated patterns for
[zai-org/GLM-5.2-FP8](https://huggingface.co/zai-org/GLM-5.2-FP8)
on 8×H200 nodes:

| Pattern | Topology | Workload |
|---------|----------|----------|
| [Single-node practical guide](glm5.2-H200-guides/agentic-serving/glm-5.2-single-node-practical-guide.md) | TP=8 + MTP, 131K ctx | Long-context agentic (Claude Code) |
| [Single-node 8K/1K optimized](glm5.2-H200-guides/agentic-serving/glm-5.2-single-node-8k1k-optimized.md) | TP=8 + MTP, 10K ctx | Short-context, high-turnover |
| [Multi-node PP=2 TP=8](glm5.2-H200-guides/agentic-serving/glm-5.2-multi-node-pp2-tp8.md) | 2 nodes, RoCE | Model/KV beyond one node's HBM |

Plus: [connecting Claude Code to vLLM](glm5.2-H200-guides/agentic-serving/claude-code-vllm-connection-guide.md)
via the native `/v1/messages` endpoint.
