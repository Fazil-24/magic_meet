# Magic Meet

Magic Meet is a meeting-native multi-agent planning system that turns live enterprise conversations into grounded solution plans, architecture recommendations, business impact summaries, and sprint-ready execution outputs. It is designed for Azure AI Foundry-style agent orchestration, where models, tools, knowledge sources, and governance work together in one workflow.

## What it does

Magic Meet helps teams move from **discussion to execution** in the same flow.

- Captures live meeting transcripts and context.
- Retrieves knowledge from internal documents such as policies, client requirements, and business metrics.
- Uses specialized agents for policy checking, architecture reasoning, business analysis, and sprint planning.
- Produces outputs such as solution briefs, architecture options, ROI views, and implementation plans.

## Problem

Enterprise meetings often produce valuable decisions, but the actual follow-through is manual, slow, and fragmented across notes, documents, and tools. Azure AI Foundry Agent Service is positioned for workflow automation through managed agent runtimes, tool orchestration, and enterprise governance, which makes it a strong fit for this kind of meeting-to-execution system.

## Proposed solution

Magic Meet uses a supervisor-led multi-agent workflow:

1. Ingest the meeting transcript and uploaded files.
2. Extract goals, risks, constraints, and unresolved questions.
3. Retrieve relevant context from the knowledge base.
4. Validate ideas against policy and guardrails.
5. Ask for human input when needed.
6. Generate architecture options and business impact views.
7. Convert the chosen path into sprint-ready work items.

## Sample knowledge base documents

This project includes sample documents that can be uploaded to a knowledge base:

- Policy and guardrails document
- Client requirements and constraints document
- Business and cost metrics document
- Sample meeting transcript

## Architecture

1.	Zoom call started.
2.	Live transcript enters the backend.
3.	Preprocessing converts transcript into structured meeting state.
4.	Supervisor agent chooses the next workflow stage.
5.	Specialist agents run sequentially or in parallel depending on stage.
6.	RAG/knowledge retrieval grounds internal decisions.
7.	Human checkpoint collects approval or extra constraints.
8.	Final supervisor synthesis creates the project plan board.

Core agent roles:

- **Supervisor Agent** – routes work across stages.
- **Policy Agent** – checks compliance and internal guardrails.
- **Knowledge Base Agent** – retrieves relevant supporting documents.
- **SME / Architecture Agent** – designs the proposed solution using internal context and targeted external research.
- **Business / ROI Agent** – evaluates impact, cost, and value assumptions.
- **Sprint Planner Agent** – turns the final direction into actionable delivery steps.

## Tech direction

Suggested stack:

- Azure AI Foundry Agent Service
- Azure AI Search or enterprise knowledge connectors
- Azure OpenAI models
- Document ingestion and transcript processing pipeline
- Workflow UI for live planning, review, and approvals


## Why it stands out

Magic Meet is not just a meeting summarizer. It is a grounded planning system that connects live conversation, enterprise knowledge, agent orchestration, and execution planning in one product experience.

