# Travel Reimbursement Approval Agent

An Agentic AI solution for evaluating employee travel reimbursement claims against company policy.

The system uses a Groq-hosted LLM as the planning layer to determine which validation tools are relevant for each claim, while deterministic Python functions perform financial calculations and enforce policy rules.

## Features

- Groq LLM-based tool selection
- Eligibility validation
- Receipt completeness checks
- Per-diem and lodging limit enforcement
- Airfare-class exception handling
- Submission timeliness validation
- Approval-threshold checks
- Duplicate-expense detection
- Policy-grounded explanations
- Tool-call audit trail
- Interactive claim submission UI
- Data-driven reimbursement dashboard
- Deterministic fallback if the LLM is unavailable

## Architecture

Claim
→ Groq LLM Planner
→ Tool Selection
→ Deterministic Python Tools
→ Policy Validation
→ Decision Engine
→ Structured Result

Possible decisions:

- APPROVE
- PARTIAL_APPROVE
- REJECT
- MANUAL_REVIEW

## Interactive Demo

The notebook includes an optional interactive form that allows a user to enter claim details and expense line items and evaluate the claim through the same agent pipeline used for the assignment claims.

![Interactive Claim Demo](assets/claim-demo.png)

## Running the Notebook

Install the required dependencies:

    pip install groq pandas matplotlib pydantic ipywidgets

Set your Groq API key as described inside the notebook and run all cells from top to bottom.

> Do not commit API keys or other secrets to the repository.

The notebook also contains a deterministic fallback so the core policy evaluation can still execute if the LLM is unavailable.

## Tech Stack

Python · Groq · Jupyter Notebook · Pydantic · Pandas · Matplotlib · ipywidgets

## Deliverable

The complete implementation, test cases, dashboard, design notes, and final structured JSON output are contained in `NipunVig.ipynb`.# Travel-Reimbursement-Agent
Agentic AI travel reimbursement system using Groq LLM tool selection, deterministic policy validation, audit trails, and an interactive claim submission demo.
