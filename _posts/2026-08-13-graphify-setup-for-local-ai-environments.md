---
layout: post
title: "Graphify Setup for Local AI Environments"
date: 2026-08-13
categories: [AI, Graphify, Setup]
author: Srini
excerpt: "A practical guide for running Graphify locally with Ollama and VS Code."
has_children: false
nav_order: 1
---

## Why this setup matters

If you want Graphify to work reliably on a local machine, the key is to match the right backend, environment, and model. This guide walks through the full setup for Windows users running Ollama and VS Code locally.

# Graphify Setup for Local AI Environments

This guide provides a consolidated workflow for configuring **Graphify** in a Windows environment, utilizing **Ollama** for local semantic extraction, and integrating the resulting knowledge graph with local VS Code orchestrators.

## Prerequisites

Before beginning, ensure the following are ready in your workspace:
1. **Virtual Environment**: Your Python `(venv)` must be activated in your PowerShell session.
2. **Local Model Server**: The **Ollama** application must be running in the background.

---

## 1. Installation

Install the Graphify CLI and its specific dependencies for local semantic extraction. Since you are operating within a virtual environment, use standard `pip`.

```powershell
pip install "graphifyy[ollama]"
```

> **Note:** Using the `[ollama]` extra ensures all necessary routing packages for local model communication are installed.

---

## 2. Environment Configuration

Ollama does not require an API key for local execution. However, Graphify may throw a warning if the expected environment variable is empty. To suppress this cosmetic warning, set a placeholder variable in your active PowerShell session:

```powershell
$env:OLLAMA_API_KEY="dummy"
```

---

## 3. Running the Extraction

Execute the extraction command. You must explicitly route the semantic parsing for non-code documents (PDFs, Markdown) through the local backend.

```powershell
graphify extract . --out ./graphify-out --no-cluster --backend ollama
```

### Specifying the Local Model

By default, the Ollama backend targets `qwen2.5-coder:7b`. If you have a specific, preferred local model pulled in Ollama, override the default using the `--model` flag:

```powershell
graphify extract . --out ./graphify-out --no-cluster --backend ollama --model qwen2.5-coder:7b
```
> **Note on Model Selection:** 
1. Ensure the model you specify is already pulled and available in your local Ollama instance. If the model is not present, Graphify will throw an error.
2. Ensure that the model you select is capable of semantic extraction. Some models may not support this feature, leading to incomplete or failed extractions.
3. Ollama service should be running in the background for the extraction to succeed.

### Handling Non-Code Documents
> **Note on Semantic Extraction:** 
> When using local Small Language Models (SLMs) via Ollama, the model may occasionally omit relational data from complex documents. You may see a terminal warning stating some dispatched files "produced no nodes." This is normal behavior for SLMs and does not impact the primary deterministic AST extraction of your codebase.

---

## 4. Integration with AI Orchestrators

Once the extraction completes, Graphify generates the structured knowledge graph at `./graphify-out/graphify-out/graph.json`. 

To leverage this within your development workflow:
* **VS Code Orchestrators (Roo Code, Cline, etc.)**: Point your local agent directly to this `graph.json` file. Provide a custom instruction in the agent's system prompt to parse this file for architectural context and node relationships prior to executing widespread repository edits.

