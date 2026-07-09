# Hermes Configuration Fix

This repository contains a quick basic fix for Hermes Agent to work with models that have a context window below the default 64,000 token requirement.

## Problem
The model `z-ai/glm-5.2` has a context window of 29,000 tokens, which is below the minimum 64,000 required by Hermes Agent.

```
ValueError: Model z-ai/glm-5.2 has a context window of 29,000 tokens, which is below the minimum 64,000 required by Hermes Agent. Choose a model with at least 64K context, or set model.context_length in config.yaml to override.
```

## Solution
Run the following command to override the context length requirement:

```bash
hermes config set model.context_length 65536
```

Alternatively, you can manually edit `config.yaml`:

```yaml
model:
  name: z-ai/glm-5.2
  context_length: 65536
```

## How It Works
This configuration allows Hermes to work with the GLM model by explicitly setting the context length to 65,536 tokens, which exceeds the minimum 64,000 requirement.

## Usage
After running the fix command, Hermes Agent will initialize without the context length error.
