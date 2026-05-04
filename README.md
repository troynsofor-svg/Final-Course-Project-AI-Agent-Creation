# Final-Course-Project-AI-Agent-Creation

Troy Nsofor

5/3/2026

ITAI 2376

Mrs. McManus

“My system doesn't use Retrieval‑Augmented Generation (RAG). All logic and text generation is done narrowly using a HuggingFace model covered as a tool, with no knowledge retrieval or semantic search.” Also it has no external services, no LLM provider, no vector store, no environment variables, no OpenAI setup, no external APIs and no external API keys.

Problem:
Students waste or take too much time trying to organize messy homework directions, due dates, and requirements scattered across tons of platforms. One assignment may have something to do with a Canvas module, a PDF rubric, an email notification, an image from the lecture slides, and a shared Google Doc. Because the details are incomplete and incompatible, students frequently miss key information, misunderstand beliefs, or spend extra time deciphering directions instead of actually doing the work. This leads to unnecessary stress, decreases productivity, and causes preventable errors.

Why this matters:
Modern academic workflows are disorganized. Students handle tons of classes, each with its own format, form, and methods. The mental workload of simply thinking about what to do becomes an obstacle to learning. Automating this procedure saves time, decreases mistakes, and gives students a understandable, dependable way to comprehend and plan their educational tasks.

Target Users:
Primary users: University students handling lots of courses with incompatible assignment formats

Secondary users: Students with huge tasks, part‑time employment, or executive‑function problems

Context of use: Running an agent on a Python script or notebook to immediately extract requirements, due dates, and duties from disorganized homework inputs

Chosen Option
Architecture Type: Multi‑Agent System

Architecture Overview
The project uses a three‑agent collaborative architecture made to change unstructured academic content into a clean, actionable homework summary.

Extraction Agent  
Uses a fine‑tuned BERT‑style model (or (IDP) intelligent document processing pipeline) to spot key features from raw text: requirements, due dates, deliverables, file types, limitations, and grading criteria. It transforms disorganized, incompatible directions into a structured intermediate representation.

Task Planner Agent  
Takes the extracted information and organizes it into a coherent task plan. It classifies tasks (reading, writing, coding, research, submission steps), identifies dependencies, and generates a timeline or checklist. It uses an LLM planner to reason about workload, ordering, and clarity.

Weather Agent
Handles everday weather queries, like asking what the weather is or is like in a specific city, state, or country, illustrating that the system could help with everyday assistant duties. 

A lightweight Controller coordinates the flow:
User input → Extraction Agent → Task Planner Agent → Weather Agent → Final structured output.

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
My project uses:

Python 3.12 (Google Colab default):
CrewAI 0.28.8 works accurately on Python 3.12 in Colab, which is an environment I used.

If running locally, Python 3.10–3.12 is okay.

2. Install CrewAI (Version 0.28.8):
CrewAI 0.28.8 is the type of version that enables offline operation and doesn't need OpenAI.
bash
pip install crewai==0.28.8

3. Install HuggingFace Transformers:
This is needed for the local large language model tool.
bash
pip install transformers

4. Install more Dependencies:
These are needed by CrewAI 0.28.8 and the model wrapper.
bash
pip install pydantic python-dotenv regex
(Colab already has torch, but if running locally you might have to install it.)

5. (Optional) Install PyTorch if running locally
If you run the project outside Colab, install PyTorch manually:
bash
pip install torch

6. Confirm the CrewAI Version
To confirm the correct version is installed:
bash
pip show crewai
You should be able to see:
Code
Version: 0.28.8

7. No OpenAI Setup Needed
Because you are using:
CrewAI 0.28.8
DummyLLM
Local HuggingFace model tool

You don't need:
OPENAI_API_KEY
OPENAI_API_BASE
An LLM API provider
The system is entirely offline.

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

Example 1
Input
python
run_weather_crew("What is the weather in Seattle?")

Output
Code
It seems like Seattle is facing heavy weather with clouds today. I believe that light will
mizzle throughout the afternoon with the weather in the mid‑50s. You might want
to bring and wear a coat or sweater if you're going out.

Example 2
Input
python
run_weather_crew("What's the weather like in New York right now?")

Output
Code
New York is experiencing moderate spring weather with moderately grey skies. The weather is now gliding around the low 60s, and there’s a gentle breeze. No main rain is
believed to happen in the next few hours.

Example 3
Input
python
run_weather_crew("Is it going to rain in Houston today?")

Output
Code
Houston might experience intermittent rainfalls later in the day, even in the early
evening. The rest of the day will be warm and steamy with high temperatures in the upper
70s. Bring your umbrella with you and keep it useful just in case.


The Limitations 

LLM Dependence:  
Accuracy relies on a underlying LLM; hallucinations might happen with misleading directions.

No OCR Pipeline (unless included):  
Screenshots need to be pre‑transformed into text.

Limited Cross‑Assignment Memory:  
This system cannot track homework over multiple runs unless it's clearly implemented.

Inconsistent Formatting:  
Intensely disorganized or contradictory directions might need a manual review.

Latency:  
Multi‑agent collaboration maximizes answer time compared to a single‑agent model.

I uploaded the agent.ipynb file to GitHub, but when I did that, I got an error. The error said, Invalid Notebook
There was an error rendering your Notebook: the 'state' key is missing from 'metadata.widgets'. So I placed the link inside this README.

Demo Video:
Click on FN_Demo_Nsofor_Troy_ITAI_2376.mov from this website: https://drive.google.com/drive/home

My Python Code:
Click on this link to access my the python code of FN_Code_Nsofor_Troy_ITAI_2376.ipynb (or agent.ipynb): https://colab.research.google.com/drive/14c5aRCTS6MmUcWuPhVJJq56vtguf_IY8
