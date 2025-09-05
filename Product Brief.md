# My Write Hand Man – Product Brief

## 📝 Overview

**My Write Hand Man** is a local-first writing assistant designed to analyze and refine essays, reflections, and letters. It runs locally on your machine, with the only external dependencies being LLM API calls (OpenAI, Anthropic, Gemini, xAI) or standard Internet usage for fact-checking and research.

The project will evolve through clear phases, starting with a lightweight MVP and growing into a full-fledged, agentic writing companion that can contextualize, debate, and refine complex bodies of work.

---

## 🎯 Project Purpose

* Support writers through analytical and critical thinking skills, such as checking **logical flow**, **redundancy**, and **tone consistency**.
* Provide broad contextual awareness: compare across a set of files or websites to identify **overlaps**, **contradictions**, and **narrative flow**.
* Concentrate expertise narrowly to **fact-check**, **analyze subjects in depth**, or **compare across disciplines**.
* Leverage multiple LLM providers to enable **LLM debates**, **collaboration sessions**, and **easy provider swapping**.
* Teach Moti how to build **agentic AI workflows**.

---

## 🛠️ Core Features

1. **Reader: Gathers knowledge of target writing**

   * Store files of writing in a dedicated folder
   * Access writing from Substack, Medium, Google Docs

2. **Summarizer: Synthesizes and summarizes writing**

   * Summarize sections in different levels of detail (ELI5 → deep analysis)
   * Combine summaries into coherent outlines

3. **Classifier: Defines attributes & analysis strategies**

   * Identify type (fiction vs. non-fiction, essay vs. reflection)
   * Recommend best practices based on type

4. **Analyst: Modular agents for targeted writing skills**

   * Logical flow checker
   * Redundancy inspector
   * Tone & coherence checker
   * Contradiction detector
   * Continuity & gap analysis
   * Analytical depth & subject expertise
   * Philosophical & cross-discipline perspectives
   * Fact-checker & researcher
   * Grammar & word choice experts
   * Grader & feedback synthesizer

5. **Skill Generator**

   * Build new expertise around user-defined topics
   * Store reusable skills for future sessions

6. **Skill Manager**

   * Measure skill usefulness based on user acceptance of feedback
   * Adapt, refine, or retire skills over time

---

## 🚦 Phased Development Roadmap

### 🟢 Phase 1 — Core MVP

**Goal:** Get a working local tool.

* Reader: load essays from `/essays`
* LLM Connector: switch between OpenAI, Claude, Gemini, xAI
* Agents: redundancy, flow, tone
* CLI tool for interaction

**Deliverable:** A working command-line assistant for essay analysis.

---

### 🟡 Phase 2 — Breadth & Retrieval

**Goal:** Expand beyond single-essay checks.

* Add vector DB (ChromaDB/FAISS) for semantic search
* Summarizer for ELI5/medium/detailed summaries
* Classifier for document tagging
* Add contradiction & continuity agents
* Enable LLM comparisons across providers

**Deliverable:** Multi-document, retrieval-aware analysis.

---

### 🟠 Phase 3 — Advanced Skills

**Goal:** Introduce skill creation and management.

* Skill Generator for defining reusable analysis prompts
* Skill Manager to evolve skills with feedback
* Add cross-discipline comparison agents

**Deliverable:** A self-extending skill system.

---

### 🔵 Phase 4 — Agentic Collaboration

**Goal:** Orchestrated, multi-agent workflows.

* Analyst agents debate and collaborate
* LLM debates and collaboration sessions
* Research & fact-check with external APIs

**Deliverable:** Agents that analyze, argue, and fact-check collaboratively.

---

### 🔴 Phase 5 — Full Writer’s Companion

**Goal:** Professional-grade environment.

* Web UI (Streamlit/Next.js)
* Session memory for persistent context
* Skill marketplace (fiction, business, academic)
* Optional local LLM integration

**Deliverable:** A polished platform: your personal editor, critic, and collaborator.

---

## 📦 Tech Stack (initial)

* **Language:** Python 3.11+
* **Libraries:**

  * `chromadb` (or FAISS) for embeddings
  * `openai`, `anthropic`, `google-generativeai`, `requests/httpx`
  * `python-dotenv` for API key management
  * `typer` or `argparse` for CLI

---

## 🚀 Example Usage (MVP)

```bash
# Check for redundancy in essay10 using Claude
python review.py --essay essay10.md --check redundancy --llm claude

# Assess logical flow in essay5 using OpenAI
python review.py --essay essay5.md --check flow --llm openai

# Compare tone across all reflections using Gemini
python review.py --essay all --check tone --llm gemini
```
