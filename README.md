# Hermes Configuration Fix

This repository contains a configuration fix for Hermes Agent to work with models that have a context window below the default 64,000 token requirement.

## Problem
The model `z-ai/glm-5.2` has a context window of 29,000 tokens, which is below the minimum 64,000 required by Hermes Agent.

## Solution
Override the context length requirement in `config.yaml`:

```yaml
model:
  name: z-ai/glm-5.2
  context_length: 65536
```

This configuration allows Hermes to work with the GLM model by explicitly setting the context length to 65,536 tokens.

## Usage
Ensure your Hermes configuration uses this `config.yaml` file when initializing the agent.
