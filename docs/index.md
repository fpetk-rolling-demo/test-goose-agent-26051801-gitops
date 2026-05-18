# test-goose-agent-26051801 — Goose Agent GitOps

This repository manages the GitOps configuration for a [Goose](https://goose-docs.ai/) AI agent deployment on OpenShift.

## Deployed Resources

| Resource   | Description                                                        |
| ---------- | ------------------------------------------------------------------ |
| Deployment | Goose agent running `ghcr.io/block/goose:latest`                     |
| Service    | ClusterIP service exposing port 3000                               |
| Route      | OpenShift Route with edge TLS termination                          |
| ConfigMap  | `test-goose-agent-26051801-goose-config` with provider and model settings |

## Configuration

The Goose agent is configured for:

- **Provider**: `openai`
- **Model**: `gpt-4o-mini`

The agent connects to the LLM provider using an API key stored in the `test-goose-agent-26051801-provider-api-key` Secret in the `goose-agent` namespace. This Secret must be created manually before the agent can communicate with the LLM provider.
