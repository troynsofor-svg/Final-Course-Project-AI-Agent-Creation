# Final-Course-Project-AI-Agent-Creation
Problem
Students waste hours trying to organize messy assignment instructions, deadlines, and requirements scattered across multiple platforms. A single assignment might involve a Canvas module, a PDF rubric, an email announcement, a screenshot from lecture slides, and a shared Google Doc. Because the information is fragmented and inconsistent, students often miss key details, misunderstand expectations, or spend more time deciphering instructions than actually completing the work. This creates unnecessary stress, reduces productivity, and leads to preventable mistakes.

Why this matters
Modern academic workflows are chaotic. Students juggle multiple classes, each with its own format, structure, and communication style. The cognitive load of simply figuring out what to do becomes a barrier to learning. Automating this process saves time, reduces errors, and gives students a clear, reliable way to understand and plan their academic tasks.

Target Users
Primary users: University students managing multiple courses with inconsistent assignment formats

Secondary users: Students with heavy workloads, part‑time jobs, or executive‑function challenges

Context of use: Running the agent through a Python script or notebook to instantly extract requirements, deadlines, and tasks from messy assignment inputs

Chosen Option
Architecture Type: Multi‑Agent System

Architecture Overview
This project implements a two‑agent collaborative architecture designed to transform unstructured academic content into a clean, actionable assignment summary.

Extraction Agent  
Uses a fine‑tuned BERT‑style model (or LLM‑based extraction pipeline) to identify key components from raw text: requirements, deadlines, deliverables, file formats, constraints, and grading criteria. It converts messy, inconsistent instructions into a structured intermediate representation.

Task Planner Agent  
Takes the extracted information and organizes it into a coherent task plan. It classifies tasks (reading, writing, coding, research, submission steps), identifies dependencies, and generates a timeline or checklist. It uses an LLM planner to reason about workload, ordering, and clarity.

A lightweight Controller coordinates the flow:
User input → Extraction Agent → Task Planner Agent → Final structured output.
