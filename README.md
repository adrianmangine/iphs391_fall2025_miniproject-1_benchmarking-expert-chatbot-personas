\# Benchmarking Expert Chatbot Personas    
\[\!\[License: MIT\](https://img.shields.io/badge/License-MIT-green.svg)\](LICENSE)    
\[\!\[Made with Python\](https://img.shields.io/badge/Made%20with-Python-blue.svg)\]()    
\[\!\[Status\](https://img.shields.io/badge/Status-Active-brightgreen.svg)\]()  

\#\# 📖 Overview  
This project benchmarks \*\*expert chatbot personas\*\* built with structured system prompts. It is part of the IPHS391 Fall 2025 Miniproject series and demonstrates how persona prompt engineering can shape chatbot behavior, evaluation, and reliability.

The repository includes:  
\- A custom chatbot persona (\`Prof. Alden Shore\`, neuroscience professor)  
\- Evaluation rubric for 10-turn conversations  
\- Chat history logs  
\- Methodology notes and reports

\---

\#\# 🧪 Methodology  
1\. \*\*Persona Design\*\*    
   \- The persona prompt defines expertise (molecular neuroscience), communication style (approachable but tough, Socratic), and editorial role (peer reviewer).    
   \- Techniques used: role specification, tone anchoring, scaffolding questions, jargon control.

2\. \*\*Conversation Benchmarking\*\*    
   \- 10-turn test conversations were run with the chatbot.    
   \- Each conversation was scored using a rubric (0–100) across criteria such as domain accuracy, tone alignment, clarity, and Socratic questioning.

3\. \*\*Meta-Prompting\*\*    
   \- Iterations of the system prompt were tested, though refinement cycles were limited due to consistently strong results.

\---

\#\# 📊 Results  
\- \*\*Consistency:\*\* Persona alignment was maintained across test runs.    
\- \*\*Strengths:\*\*    
  \- Clear definitions of technical terms    
  \- Stepwise explanations with guiding questions    
  \- Balanced tone (encouraging but critical)    
\- \*\*Limitations:\*\*    
  \- Few iterations performed; broader testing could improve robustness.  

Rubric scores consistently showed high fidelity to the intended expert persona.

\---

\#\# 📂 Files Description  
\- \`chatbot\_code.md\` — Example code for running the chatbot persona.    
\- \`prompt\_persona.txt\` — Full system prompt defining the persona.    
\- \`chat\_history.md\` — Transcript of evaluation conversations.    
\- \`chat\_rubric.txt\` — Rubric used for scoring chatbot persona quality.    
\- \`chat\_rubric\_history.md\` — Notes on rubric development and revisions.    
\- \`metaprompt\_history.txt\` — Documentation of prompt refinement cycles.    
\- \`mp1\_chatbot\_report.txt\` — Written project report summarizing methods and outcomes.

\---

\#\# 🚀 Usage Instructions  
1\. Clone the repository:    
   \`\`\`bash  
   git clone https://github.com/adrianmangine/iphs391\_fall2025\_miniproject-1\_benchmarking-expert-chatbot-personas.git  
   cd iphs391\_fall2025\_miniproject-1\_benchmarking-expert-chatbot-personas

