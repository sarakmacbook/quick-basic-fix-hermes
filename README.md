# Hermes Configuration Fix

This repository contains a quick basic fix for Hermes Agent.

## The Problem & Solution

ValueError: Model z-ai/glm-5.2 has a context window of 29,000 tokens, which is 
below the minimum 64,000 required by Hermes Agent. Choose a model with at least 
64K context, or set model.context_length [...]

Run the following command to override:
```bash
hermes config set model.context_length 65536
```
