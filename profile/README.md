# Inferbase

**The control plane for AI models: route, govern, observe.**

One OpenAI-compatible API for every model. Send `model: "auto"` and each request is routed to the
best model for the task on quality, cost and latency, with the reason kept on record.

- **Smart Routing.** Each request is classified and served by the model that fits it. The response
  says which model answered and why.
- **Fallback.** When a provider fails or is busy, the request moves to the next route.
- **Policies and guardrails.** Assign routing policies, guardrails, spend limits and rate limits to
  each API key.
- **Your credentials or ours.** Run on Inferbase-managed models, your own provider keys, your cloud
  account (Azure, AWS Bedrock, Google Vertex) or a self-hosted endpoint.
- **Logs and usage.** Every request is recorded with its model, cost and routing decision.

## Quickstart

Use the OpenAI SDK you already have and change the base URL.

```python
from openai import OpenAI

client = OpenAI(
    api_key="inf_your_api_key",
    base_url="https://api.inferbase.ai/api/v1/inference",
)

response = client.chat.completions.create(
    model="auto",
    messages=[{"role": "user", "content": "Summarize the causes of the 2008 financial crisis in three sentences."}],
)

print(response.model)                      # the model that served the request
print(response.choices[0].message.content)
```

[Create an account](https://inferbase.ai/register), make an API key, and follow the
[quickstart](https://inferbase.ai/docs/getting-started/quickstart). There is a free plan.

## Repositories

| Repository | What it is |
|---|---|
| [inferbase-build-guides](https://github.com/InferbaseAI/inferbase-build-guides) | Runnable applications behind the [build guides](https://inferbase.ai/solutions): support assistants, RAG, agents, extraction and voice |

## Free tools

- [Model catalog](https://inferbase.ai/models) and [side-by-side comparison](https://inferbase.ai/compare)
- [GPU capacity planner](https://inferbase.ai/gpu-capacity-planning)
- [Token counter](https://inferbase.ai/token-counter)

## Links

[Website](https://inferbase.ai) · [Docs](https://inferbase.ai/docs) · [Pricing](https://inferbase.ai/pricing) ·
[Design partners](https://inferbase.ai/design-partners) · [X](https://x.com/inferbase) · hello@inferbase.ai
