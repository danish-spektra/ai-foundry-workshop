# Azure AI Foundry Workshop — Notebooks

This directory contains the hands-on Jupyter notebooks for the workshop. They target the **New Microsoft Foundry** experience (endpoint-based project client) and authenticate **keyless** with Microsoft Entra ID.

## Setup

1. **Sign in to Azure** (keyless authentication uses this identity):
   ```bash
   az login
   ```

2. **Create/activate the virtual environment and install dependencies** (from the repository root):
   ```bash
   python -m venv .venv
   .venv\Scripts\activate        # Windows (PowerShell)
   # source .venv/bin/activate   # macOS / Linux
   pip install -r 2-notebooks/requirements.txt
   ```

3. **Configure `.env`** — copy `.env.example` (in the repository root) to `.env` and fill in your `PROJECT_ENDPOINT`, model deployment names, and Azure AI Search values. No project or model API keys are required; authentication is via `az login`.

4. **Select the kernel** — open a notebook in VS Code and choose the workshop Python environment as the kernel.

## Notebooks

| Folder | Notebook | Focus |
| --- | --- | --- |
| `1-chat_completion` | `1-basic-chat-completion.ipynb` | Chat completions via `AIProjectClient.get_openai_client()` |
| | `2-embeddings.ipynb` | Text embeddings with `text-embedding-3-large` |
| | `3-basic-rag.ipynb` | Basic RAG over an Azure AI Search vector index |
| | `4-phi-4.ipynb` | Reasoning with the Phi-4 model |
| | `5-deep-seek-v3.ipynb` | DeepSeek-V3.2 for travel and technical problem solving |
| `2-agent_service` | `1-basics.ipynb` | Create a prompt agent (Responses API) |
| | `2-code_interpreter.ipynb` | Code Interpreter tool (BMI + nutrition charts) |
| | `3-file-search.ipynb` | File Search over a vector store |
| | `4-web-search.ipynb` | Web Search tool with URL citations |
| | `5-agents-aisearch.ipynb` | Azure AI Search tool grounded on an index |
| `3-quality_attributes` | `1-Observability.ipynb` | OpenTelemetry tracing + Azure Monitor |
| `4-frameworks` | `1-rag-sk-agents-aisearch.ipynb` | Semantic Kernel agent + Azure AI Search (RAG) |
| | `2-autogen-multi-agent-rag.ipynb` | AutoGen multi-agent RAG pipeline |

> All agent notebooks create an agent, let you view it in the Foundry portal under **Build → Agents**, and then delete it at the end so your project stays tidy.
