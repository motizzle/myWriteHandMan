# Essay Review Agent

A local-first writing assistant designed to help analyze and refine essays, reflections, and letters. The tool runs locally on your machine with the only external dependency being an LLM API call (OpenAI, Anthropic, Gemini, or xAI).

## 🎯 Project Purpose

* Support writers by checking **logical flow**, **redundancy**, and **tone consistency** across multiple essays.
* Allow **cross-essay awareness**: identify when content overlaps, contradicts, or repeats.
* Provide a flexible framework to swap between different LLM providers.
* Serve as a foundation for experimenting with **agentic AI workflows**.

## 🛠️ Core Features (MVP)

1. **Essay Loading**

   * Store essays as plain text or Markdown files in `/essays`.

2. **Redundancy Check**

   * Compare one essay against the rest and highlight overlapping or repetitive content.

3. **Flow Check**

   * Assess whether an essay’s reflection flows logically from its letter.

4. **Tone Check**

   * Compare style, tone, and perspective across reflections for consistency.

5. **LLM Flexibility**

   * Ability to select which LLM provider to call per request (OpenAI, Claude, Gemini, xAI).

## 📐 System Architecture

**1. Data Layer**

* `/essays` folder holds source text.
* Loader reads files; optional embeddings stored in ChromaDB for semantic search.

**2. Processing Layer**

* Chunker: splits long essays into segments.
* Retriever: fetches relevant essays or chunks.

**3. LLM Connector Layer**

* Abstract wrapper for calling different LLM APIs.
* Configurable via `.env` file for API keys.

**4. Agent Layer**

* FlowChecker Agent
* RedundancyChecker Agent
* ToneChecker Agent
* Indexer Agent (updates essay index)

**5. User Interface Layer**

* CLI tool (`review.py`).
* Command-line arguments for essay, check type, and LLM provider.

## 📦 Tech Stack

* **Language:** Python 3.11+
* **Libraries:**

  * `chromadb` (or FAISS) for embeddings
  * `openai`, `anthropic`, `google-generativeai`, `requests/httpx`
  * `python-dotenv` for API key management
  * `typer` or `argparse` for CLI

## 🚀 Usage Examples

```bash
# Check for redundancy in essay10 using Claude
python review.py --essay essay10.md --check redundancy --llm claude

# Assess logical flow in essay5 using OpenAI
python review.py --essay essay5.md --check flow --llm openai

# Compare tone across all reflections using Gemini
python review.py --essay all --check tone --llm gemini
```

## 🔮 Future Extensions

* Web UI (Streamlit or Gradio) for easier interaction.
* Multi-agent orchestration (CrewAI, LangChain) to let agents collaborate.
* Fine-tuned local embedding model for offline similarity search.
* Export results in structured JSON/Markdown reports.

---

## ✅ Next Steps

1. Scaffold repo with:

   * `/essays`
   * `/agents`
   * `/llm_providers`
   * `review.py`
   * `README.md`
2. Implement basic LLM connector.
3. Build first agent: **RedundancyChecker**.
4. Iterate with Flow and Tone agents.