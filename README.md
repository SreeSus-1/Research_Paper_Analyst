# Research_Paper_Analyst
A multi-agent system that reads research PDFs, builds context, searches the web, and generates a clear summary
🚀 Overview

This project implements a multi-agent workflow powered by Google’s Agent Development Kit (ADK) and Gemini 2.0, designed to:

Read PDF text

Extract structured content

Build a condensed context

Generate a student-friendly summary

Evaluate clarity & correctness

Finally produce a detailed, multi-section research summary

The system follows a sequential tool-using agent architecture, similar to real-world agent pipelines used in industry.

🧠 System Architecture (Agentic Workflow)

The system contains five agents:

1️⃣ Document Reader Agent

Extracts structured Markdown from raw PDF text
(Cleans OCR noise, identifies sections like Title, Abstract, Methods, Results…)

2️⃣ Context Builder Agent

Compresses the extracted content into a 500–700 word context
(Preserves technical meaning while removing clutter)

3️⃣ Summarizer Agent

Generates a clear, student-friendly explanation with sections:

Problem

Method

Data

Results

Key Takeaways

4️⃣ Evaluation Agent

Checks clarity, correctness, coverage
(Returns reviewer-style bullet feedback)

5️⃣ Research Analyst Agent (Root Agent)

Controls the workflow and decides tool order
Outputs the final structured summary only



flowchart TD

UserInput["📄 User PDF Text"]

DocumentReader["📘 Document Reader Agent"]
ContextBuilder["🧩 Context Builder Agent"]
Summarizer["📝 Summarizer Agent"]
Evaluator["🔍 Evaluation Agent"]

ResearchAnalyst["🤖 Research Analyst Root Agent"]

UserInput --> ResearchAnalyst
ResearchAnalyst -->|1. call| DocumentReader
DocumentReader -->|structured content| ContextBuilder
ContextBuilder -->|context| Summarizer
Summarizer -->|summary| Evaluator
Evaluator -->|feedback| ResearchAnalyst
ResearchAnalyst --> FinalOutput["📌 Final Detailed Summary"]
