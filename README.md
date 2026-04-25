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

Frameworks, Tools, and Services
Programming Language: Python 3.11

Agent Framework: CrewAI 

LLM Provider: OpenAI (e.g., GPT‑4o‑mini or GPT‑4o)

Vector Store: ChromaDB

Embeddings: text‑embedding‑3‑small

Environment Management: python-dotenv

Other Libraries:

rich — CLI formatting

pydantic — schema validation

typer — CLI interface (if used)

Installation
1. Clone the repository
bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
2. Create and activate a virtual environment
bash
python -m venv .venv
source .venv/bin/activate   # macOS / Linux
.venv\Scripts\activate      # Windows
3. Install dependencies
bash
pip install -r requirements.txt
Environment Variables
Create a .env file in the project root:

bash
OPENAI_API_KEY="your-api-key-here"
MODEL_NAME="gpt-4o-mini"
Add any additional variables your architecture requires.

Running the Agent
Command Line
bash
python main.py
Or with direct input:

bash
python main.py --input "Here is my assignment text..."
Notebook Demo
Open notebooks/demo.ipynb

Run all cells

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

Demo Video
Add your recorded walkthrough here:

markdown
[Demo Video (YouTube / Loom)](https://your-demo-link)
