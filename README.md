# Email Agent — LLM Arbiter (Mini POC)

## Overview
This repository provides the dataset and task description for a **24-hour technical assignment**.

The goal is to implement a **simplified AI Email Agent** able to:
1. Load and normalize a dataset of emails (JSONL format)
2. Reconstruct conversation threads — even when technical fields are missing
3. Identify or tag key events (e.g. proposal, approval, confirmation, rejection, request)
4. Optionally use an **LLM Arbiter (Google Gemini)** to validate ambiguous relationships between emails

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
If you decide to integrate the **LLM Arbiter**:
1. Use this Api key AIzaSyDT8UUuWORYe_hmzTEIJ1qDd4HJFmxJ2gY
2. Export it as an environment variable:
   ```bash
   export GOOGLE_API_KEY="AIzaSyDT8UUuWORYe_hmzTEIJ1qDd4HJFmxJ2gY"


---

## Deliverables
- Your full codebase (Python)
- A short `README.md` explaining your approach and architecture
- Example output or logs

Good luck!
