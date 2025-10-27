# Automation Workflow Portfolio (n8n)

Welcome! This repository serves as my portfolio of advanced automation workflows, demonstrating skills in n8n, systems integration, and the application of AI and agents.

Each workflow is contained in its own folder, complete with its `.json` file and a detailed `README.md`.

## Workflow Gallery

Here is an overview of the workflows in this portfolio. Click the image or title to see the full details for each one.

| Preview | Workflow | Brief Description | Key Technologies |
| :---: | :--- | :--- | :--- |
| [![Mini-RAG Preview](./rag-validation/flow-preview.png)](./rag-validation/) | **Compliance Validation (Mini-RAG)** | A flow that uses RAG to validate an input JSON against a PDF of business rules. | `n8n` `AI` `Python` `VectorDB` |
| [![Secretary Preview](./support-triage/flow-preview.png)](./support-triage/) | **Secretary** | Monitors a channel and uses AI to classify, prioritize, and route support tickets. | `n8n` `AI` `Python` `PostgreSQL` |
| [![Personal Assistant Preview](./news-scout/flow-preview.png)](./news-scout/) | **Personal Assistant** | An agent that scans news sources, selects the most relevant article, and generates a summary. | `n8n` `AI` `Python` |

---

### How to Use
To import any of these workflows into your n8n instance:

1.  Navigate to the desired workflow's folder (e.g., `/rag-validation/`).
2.  Download the `.json` file (e.g., `workflow-rag.json`).
3.  In your n8n instance, go to **Import** > **From File** and select the `.json` file.
4.  Configure the necessary credentials (APIs, databases, etc.).
