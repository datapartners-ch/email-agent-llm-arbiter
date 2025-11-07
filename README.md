# Email Agent — LLM Arbiter

## Overview
This repository provides the dataset and task description for a **24-hour technical assignment**.

The goal is to implement a **simplified AI Email Agent** able to:
1. Load and normalize a dataset of emails (JSONL format)
2. Reconstruct conversation threads — even when technical fields are missing
3. Identify or tag key events (e.g. proposal, approval, confirmation, rejection, request)
4. Optionally use an **LLM Arbiter (Google Gemini)** to validate ambiguous relationships between emails
5. Demonstrate a **basic RAG-like interaction**, where the system can answer simple natural language questions based on the reconstructed threads.

The solution should demonstrate your ability to design, structure, and document a modular Python-based pipeline.

---

## Dataset
- Path: `data/raw/emails.jsonl`
- Format: one JSON object per line.
- Each record includes:
  ```json
  {
    "id": "12345",
    "from": "john@pedrali.it",
    "to": ["maria@pedrali.it"],
    "date": "2023-04-01T09:23:00",
    "subject": "Re: Paint color issue",
    "body": "We should stop the order until quality confirms...",
    "in_reply_to": "12344",
    "references": ["12341", "12342", "12343", "12344"]
  }


---

## Guidelines
You are free to design the solution as you prefer.  
We recommend structuring the project in a modular way (e.g. `data_layer.py`, `thread_builder.py`, etc.).

- Document your approach clearly.  
- The output can be printed to the console or written to JSON.  
- You can optionally demonstrate a simple semantic query (e.g., "Who approved the proposal?").

---

## Gemini API (Optional)
If you decide to integrate the **LLM Arbiter** you can create a free api key with Google AI Studio

---

## Deliverables
- Your full codebase (Python)
- A short `README.md` explaining your approach and architecture
- Example output and logs (optional)

 ---

## Cost & Architecture Assessment (Optional)

### Goal

Provide a cost estimation and reference architecture for scaling the Email Agent — LLM Arbiter system to handle a real-world dataset of 100 GB of emails, covering the full AI and semantic-search (RAG) workflow.

You must:
* Define assumptions  
* Propose a final architecture (diagram or descriptive schema)
* Estimate operational and setup costs (OPEX / CAPEX)
* Justify technology choices (e.g., PostgreSQL vs DynamoDB, Pinecone vs Chroma, Mistral vs GPT)
* Discuss main trade-offs (cost vs quality, scalability vs maintenance, cloud vs on-prem)

---

### Context Data

* **POC Volume:** 100 GB of emails + attachments
* **System Goal:** semantic archiving + thread reconstruction + event insight + RAG QA
* **Expected Load:**
    * 1,000 RAG queries / month
    * 100 new attachments / month
* **Reference AI Models:**
    * Embedding → all-MiniLM-L12-v2 (open source, local)
    * LLM → Mistral 7B Instruct or GPT-4-mini (API or managed inference)

---

### Expected Deliverables

#### 1. Assumptions

#### 2. Final Architecture (Diagram or Description)

#### 3. Cost Estimation Table


#### 4. Final Commentary (max 300 words)

Good luck!
