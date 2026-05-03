Details on Whether I Upgraded from the Midterm Plan 

I’ve definitely upgraded and crucially improved my system from my midterm plan. 

When I was doing the midterm, my plan was to use a two‑agent system with a BERT extractor and a BERT task classifier. The last system continues to follow the structure ideally. However, the implementation changed because of technical problems and the facts of using Crew AI. 

What changed from my midterm plan: 

I really planned to combine the fine-tuned BERT models immediately with the agents. 

Crew AI’s architecture needed the LLM object with a .bind() technique, which BERT didn’t provide. 

Crew AI 1.14.3 forced, wanted, and required OpenAI validation, which stopped the offline procedure. 

I changed from Crew AI 1.14.3 to Crew AI 0.28.8 and offered a Dummy LLM to fulfill the framework’s needs. 

Rather than embedding BERT immediately, I covered and used the Hugging Face large language model as a tool, which these agents call for AI-generated content. 

I added a third agent, which is the weather agent. 


The reasons why they changed:

The changes were mandatory to confirm: 

offline access 

balanced execution 

consistency with Crew AI’s internal LLM likelihoods 

Escape of the OpenAI API model errors 

I added a third agent (the weather agent), due to this project requiring the illustrations of three real‑world scenarios, and the midterm plan just had two agents. Including the weather agent enabled me to describe that the system could deal with digital assistant duties further from academic workflows. It even described the configurability of the architecture. It used the same local Hugging Face model tool and Dummy LLM tool just like the other agents, meaning that this system could increase with no remodeling. The addition strengthened the demo, fulfilled the homework needs, and illustrated that the multi‑agent model could help with both specific and everyday duties. 

This last system is now stronger and simpler to preserve than the regular blueprint. 

The things that worked: 
The multi‑agent pipeline successfully processed the disorganized directions, and it created machine-readable outputs. 
The local Hugging Face model tool functioned dependably, and it kept my system entirely offline. 
The agents successfully teamed up through the Crew AI sequential groups. 
My last system became balanced and reproducible. 

The things that did not work: 
Crew AI 1.14.3 forced, wanted, and required OpenAI validation, breaking the offline procedure. 
BERT models couldn’t be combined directly because of Crew AI’s .bind() needs. 
Crew AI version 1.14.3 made confusing or ambiguous error messages. 
Google Colab kept on attempting to update packages, causing version problems. 

How I handled it:
I switched from Crew AI 1.14.3 to Crew AI 0.28.8.
I made Dummy LLM that fulfills Crew AI’s internal LLM needs. 
I used and covered the Hugging Face model as a tool, so that the agents can continue to create text.
I deleted every OpenAI import and environment variable
I redesigned the agents' meanings to match Crew AI 0.28.8’s fundamental structure. 

The Biggest Technical Challenge and How it was Solved 

The biggest main problem was Crew AI's rigid LLM evaluation and its model behavior. 

Problems I faced:
Crew AI 1.14.3 did not want to run without OpenAI API keys. 
When naming the local model, Crew AI made attempts to validate OpenAI API keys. 
Crew AI needed the LLM object with a .bind() technique, which the local model tool didn’t possess.
Multiple hidden validation layers lead to a lot of errors such as:

"LocalLLMWrapper doesn't have no attribute 'bind'" 
"OpenAI API key is lost" 
"Connection failed to OpenAI API" 
“OpenAI API key is needed” 
“1 value error for CustomLocalLLM index error, Model name is needed and can't be empty” 

How I solved the problems: 
I changed from Crew AI version 1.14.3 to Crew AI version 0.28.8, which enables offline procedures. 
I deleted every OpenAI import and environment variable to stop fallback validation mistakes. 
I made a Dummy LLM that fulfills Crew AI’s internal LLM needs. 
I used the Hugging Face model as a tool, so that the agents can continue to create text. 
I redesigned the agent meanings to match Crew AI 0.28.8’s fundamental structure.

The integration finally created a balanced, fully offline multi‑agent model. 

If I began another semester of AI in school, I would create a personal finance agent that would track my income and the money I spent and saved in my account. 
This could also be a agentic analytics agent that helps with identifying financial activity, classifying transactions, and creating summaries or insights. 
Additionally, it can play the roles as a planning and monitoring agent, just like my current system, but concentrated on budgeting and digital banks. 
Lastly, this type of agent would even depend vastly on tools, like spreadsheets or AI data structuring tools to store and oberserve financial data.
