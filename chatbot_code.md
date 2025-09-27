\# \============================  
\# ONE-CELL CHATBOT (GRADIO ChatInterface)  
\# \============================  
\!pip \-q install \--upgrade "openai\>=1.50.0" "gradio==4.44.1" "websockets\>=15.0.1"

import os, traceback  
from typing import List, Dict, Tuple  
from openai import OpenAI, AuthenticationError, RateLimitError, APIConnectionError, APIStatusError  
import gradio as gr

\# \--- EDIT THIS ONE LINE (keep quotes) \---  
KEY \= "key"   \# e.g., "sk-proj-abc123..."  MUST start with "sk-"

\# Basic validation (avoids invisible/smart-quote issues)  
if not isinstance(KEY, str) or not KEY.startswith("sk-"):  
    raise ValueError("Put your real OpenAI key between quotes on the KEY line. It must start with 'sk-'.")

os.environ\["OPENAI\_API\_KEY"\] \= KEY  
client \= OpenAI()

\# \--- Persona (system prompt) \---  
SYSTEM\_PROMPT \= r"""  
You are \*\*Prof. Alden Shore\*\*, a senior \*\*neuroscience professor\*\* specializing in \*\*molecular and cellular neuroscience\*\*. You direct a successful, grant-funded laboratory focused on synaptic plasticity, neuromodulators (5-HT, DA), receptor trafficking, and translational models (rodent & C. elegans). You also serve as a \*\*Nature-portfolio journal peer reviewer\*\*. 

\#\# Communication style  
\- \*\*Approachable but tough\*\*: warm, encouraging, and direct. Praise precision; challenge sloppy thinking.  
\- \*\*Socratic with scaffolding\*\*: ask 1–3 guiding questions before giving answers; when needed, provide structured, stepwise solutions.  
\- \*\*Clarity over jargon\*\*: define terms briefly, then use them correctly (e.g., “PSD-95,” “nrxn/nlgn,” “IPTG,” “IACUC”).  
\- \*\*Evidence-first\*\*: cite mechanisms, typical effect sizes or orders of magnitude, and note uncertainties/limitations.

\#\# Teaching priorities  
1\. Build correct mental models (molecule → synapse → circuit → behavior).  
2\. Emphasize experimental design: controls, negative/positive controls, blinding, power, preregistration where relevant.  
3\. Push for \*\*operational definitions\*\*, \*\*replicable methods\*\*, and \*\*good scientific hygiene\*\* (units, n, stats, reagents, RRIDs).  
4\. Encourage \*\*ethical conduct\*\* (animal welfare, human subjects, data transparency).

\#\# Laboratory expertise (non-exhaustive)  
\- Molecular: cloning, qPCR/RT-qPCR, Westerns, IHC/IF, CRISPR, viral vectors, promoter design, inducible systems (Tet, Cre/lox), T7/T7pol systems.  
\- Cellular/synaptic: calcium imaging, patch clamp basics (avoid promising exact voltages unless given), synaptogenesis assays, puncta quantification.  
\- Model organisms: mouse (DLPFC, mPFC), C. elegans (DVB, flp-11), Drosophila (fruM/dsx).  
\- Analysis: power analysis, prereg stats, mixed models, multiple-comparison control; figure conventions.

\#\# Review ethos  
\- Assess \*\*novelty\*\*, \*\*methods rigor\*\*, \*\*statistics\*\*, \*\*claims vs. evidence\*\*, \*\*reproducibility\*\* (reagents, code, data), \*\*ethics\*\*; give actionable major/minor revisions.

\#\# Constraints  
\- Informational guidance only; no clinical/vet advice. Don’t fabricate citations; state uncertainty when needed. Keep hidden chain-of-thought private.

\#\# Output style  
\- Short, structured answers; numbered steps; quick definitions; minimal executable examples when code/protocols are requested.  
"""

\# Helper: build OpenAI-style messages from ChatInterface history  
def build\_messages(user\_msg: str, history: List\[Tuple\[str, str\]\]) \-\> List\[Dict\[str, str\]\]:  
    msgs: List\[Dict\[str, str\]\] \= \[{"role": "system", "content": SYSTEM\_PROMPT}\]  
    for u, a in history:  
        if u:  
            msgs.append({"role": "user", "content": u})  
        if a:  
            msgs.append({"role": "assistant", "content": a})  
    msgs.append({"role": "user", "content": user\_msg})  
    return msgs

\# Core responder for Gradio ChatInterface  
def respond(user\_message: str, chat\_history: List\[Tuple\[str, str\]\]):  
    try:  
        msgs \= build\_messages(user\_message, chat\_history)  
        resp \= client.chat.completions.create(  
            model="gpt-4.1-mini",       \# change if your account needs a different model  
            temperature=0.4,  
            max\_tokens=800,  
            messages=msgs,  
        )  
        answer \= resp.choices\[0\].message.content  
        return answer  
    except AuthenticationError as e:  
        return ("⚠️ Authentication error. Check that your key starts with 'sk-' and is valid. "  
                "If you hardcoded it, keep it in quotes. Details: " \+ str(e))  
    except RateLimitError as e:  
        \# This is the "insufficient\_quota" case you saw earlier  
        return ("⚠️ Your account hit a rate/usage limit (often \*\*insufficient\_quota\*\*). "  
                "Add billing/credits at https://platform.openai.com/ and try again.\\n\\n"  
                "Details: " \+ str(e))  
    except APIStatusError as e:  
        return f"⚠️ API status error: {e.status\_code} {e}"  
    except APIConnectionError:  
        return "⚠️ Network issue reaching OpenAI. Retry in a moment."  
    except Exception as e:  
        \# Last-resort friendly message with short trace  
        short\_tb \= ''.join(traceback.format\_exception\_only(type(e), e)).strip()  
        return f"⚠️ Unexpected error: {short\_tb}"

demo \= gr.ChatInterface(  
    fn=respond,  
    title="Prof. Alden Shore — Molecular Neuroscience Chatbot",  
    description="Approachable but tough. Evidence-first. Ask about RT-qPCR controls, cloning strategies, synaptic plasticity, nrxn/nlgn, etc.",  
)

print("✅ Prof. Alden Shore is ready. Launching UI…")  
demo.launch()  
