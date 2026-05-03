What worked: 
The multi‑agent pipeline successfully processed the disorganized directions, and it created machine-readable outputs. 
The local Hugging Face model tool functioned dependably, and it kept the system entirely offline. 
The agents successfully teamed up through the Crew AI sequential groups. 
The last system became balanced and reproducible. 

What did not work: 
Crew AI 1.14.3 forced, wanted, and required OpenAI validation, breaking the offline procedure. 
BERT models couldn’t be combined directly because of Crew AI’s .bind() needs. 
Crew AI version 1.14.3 made confusing or ambiguous error messages. 
Google Colab kept on attempting to update packages, causing version problems. 

How I handled it:
I transferred from Crew AI 1.14.3 to Crew AI 0.28.8.
I made Dummy LLM that fulfills Crew AI’s internal LLM needs. 
I used the Hugging Face model as a tool, so that the agents can continue to create text.

The Biggest Technical Challenge and How it was Solved 

The biggest main problem was Crew AI's rigid LLM evaluation and its model behavior. 

Problems I faced:
Crew AI 1.14.3 did not want to run without OpenAI API keys. 
When naming the local model, Crew AI made attempts to validate OpenAI API keys. 
Crew AI needed the LLM object with a .bind() technique, which the local model tool didn’t possess.

Multiple hidden validation layers lead to a lot of errors such as: 
"LocalLLMWrapper has no attribute 'bind'" 
"OpenAI API key missing" 
"Failed to connect to OpenAI API" 
“OpenAI API key is required” 
“1 validation error for CustomLocalLLM Value error, Model name is required and cannot be empty” 

How I solved the problems: 
I changed from Crew AI version 1.14.3 to Crew AI version 0.28.8, which enables offline procedures. 
I deleted every OpenAI import and environment variable to stop fallback validation mistakes. 
I made a Dummy LLM that fulfills Crew AI’s internal LLM needs. 
I used the Hugging Face model as a tool, so that the agents can continue to create text. 
I redesigned the agent meanings to match Crew AI 0.28.8’s fundamental structure. 
The integration finally created a balanced, fully offline multi‑agent model. 

If I began another semester of AI in school, I would create a personal finance agent that would track my income and the money I spent and saved on my account. 
This could also be a agentic analytics agent that helps with spotting financial activity, grouping transactions, and creating summaries or insights. 
Additionally, it can play the roles as a planning and monitoring agent, just like my current system, but concentrated on budgeting and digital banks. 
Lastly, this type of agent would even depend vastly on tools, like spreadsheets or AI data structuring tools to store and oberserve financial data.
