# Final-Course-Project-AI-Agent-Creation

“My system doesn't use Retrieval‑Augmented Generation (RAG). All logic and text generation is done narrowly using a HuggingFace model covered as a tool, with no knowledge retrieval or semantic search.” Also it has no external services, no LLM provider, no vector store, no environment variables, no OpenAI setup, no external APIs and no external API keys.

Problem:
Students waste or take too much time trying to organize messy homework directions, due dates, and requirements scattered across tons of platforms. One assignment may have something to do with a Canvas module, a PDF rubric, an email notification, an image from the lecture slides, and a shared Google Doc. Because the details are incomplete and incompatible, students frequently miss key information, misunderstand beliefs, or spend extra time deciphering directions instead of actually doing the work. This leads to unnecessary stress, decreases productivity, and causes preventable errors.

Why this matters:
Modern academic workflows are disorganized. Students handle tons of classes, each with its own format, form, and methods. The mental workload of simply thinking about what to do becomes a obstacle to learning. Automating this procedure saves time, decreases mistakes, and gives students a understandable, dependable way to comprehend and plan their educational tasks.

Target Users:
Primary users: University students handling lots of courses with incompatible assignment formats

Secondary users: Students with huge tasks, part‑time employment, or executive‑function problems

Context of use: Running an agent on a Python script or notebook to immediately extract requirements, due dates, and duties from disorganized homework inputs

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

Frameworks, Tools, and Services
Programming Language: Python 3.12

Agent Frameworks: 
CrewAI (version 0.28.8)
Transformers (HuggingFace)
Python Standard Library

Libraries:
rich — CLI formatting
pydantic — schema validation
typer — CLI interface (if used)

Tools:
Local Model Tool (HuggingFace Model Wrapper)
Dummy LLM
Weather Tool (simple text‑generation call)

Installation Steps:
1. Python Version
Your project uses:

Python 3.12 (Google Colab default)
CrewAI 0.28.8 works correctly under Python 3.12 in Colab, which is the environment you used.

If running locally, Python 3.10–3.12 is safe.

2. Install CrewAI (Version 0.28.8)
CrewAI 0.28.8 is the version that allows offline operation and does not require OpenAI.

bash
pip install crewai==0.28.8
3. Install HuggingFace Transformers
This is required for your local text‑generation model tool.

bash
pip install transformers
4. Install Additional Dependencies
These are required by CrewAI 0.28.8 and your model wrapper.

bash
pip install pydantic python-dotenv regex
(Colab already includes torch, but if running locally you may need to install it.)

5. (Optional) Install PyTorch if running locally
If you run the project outside Colab, install PyTorch manually:

bash
pip install torch
6. Verify CrewAI Version
To confirm the correct version is installed:

bash
pip show crewai
You should see:

Code
Version: 0.28.8
7. No OpenAI Setup Required
Because you are using:

CrewAI 0.28.8

DummyLLM

Local HuggingFace model tool

You do not need:
OPENAI_API_KEY
OPENAI_API_BASE

Any external LLM provider

Your system is fully offline.
Modify the input cell to test different assignment instructions

Example Usage
Example 1 — Extracting Requirements
Input:

Code
Assignment 3: Research Reflection
Due next Friday before 11:59pm.
Write 2–3 pages reflecting on your research process.
Include at least 3 sources. Submit as a PDF on Canvas.
Also complete the peer review by Sunday.
Output (excerpt):

Code
Assignment: Research Reflection
Due Date: Friday, 11:59pm

Extracted Requirements:
- 2–3 page reflection on research process
- Minimum 3 sources
- PDF submission on Canvas
- Peer review due Sunday

Planned Tasks:
1. Read and annotate 3 sources
2. Draft reflection (2–3 pages)
3. Revise and export as PDF
4. Submit PDF to Canvas
5. Complete peer review
Example 2 — Combining Messy Inputs
Input:

Code
Canvas page says: "Submit the video presentation by April 12."
Rubric PDF says: "Presentation must be 5–7 minutes."
Email says: "Don't forget to upload your slides as well."
Output (excerpt):

Code
Assignment: Video Presentation
Due Date: April 12

Extracted Requirements:
- 5–7 minute video presentation
- Upload slide deck
- Submit both files to Canvas

Planned Tasks:
1. Draft slide deck
2. Record 5–7 minute video
3. Export video file
4. Upload video and slides to Canvas
Example 3 — Checklist Mode
Input:

Code
"Make me a checklist for this assignment."
Output:

Code
Checklist:
[ ] Draft slide deck
[ ] Record 5–7 minute video
[ ] Export video file
[ ] Upload video to Canvas
[ ] Upload slides to Canvas

Known Limitations
LLM Dependence:  
Accuracy depends on the underlying LLM; hallucinations may occur with ambiguous instructions.

No OCR Pipeline (unless added):  
Screenshots must be pre‑converted to text.

Limited Cross‑Assignment Memory:  
The system does not track assignments across multiple runs unless explicitly implemented.

Inconsistent Formatting:  
Extremely chaotic or contradictory instructions may require manual review.

Latency:  
Multi‑agent coordination increases response time compared to a single‑agent system.

Demo Video:
Click on FN_Demo_Nsofor_Troy_ITAI_2376.mov from this website: https://drive.google.com/drive/home
