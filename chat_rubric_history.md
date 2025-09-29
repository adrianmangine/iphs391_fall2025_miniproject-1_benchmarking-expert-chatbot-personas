# Chatbot persona rubric


## Prompt:
chat\_history.md

File

You are an expert in AI evaluation metrics and prompt engineering. Help me create a comprehensive scoring rubric for evaluating chatbot persona quality.

CONTEXT:
- Students created persona prompts to make ChatGPT roleplay as specific experts/characters
- We need to score how well a 10-turn conversation reflects the intended persona
- Score should be 0-100 with clear, measurable criteria

PERSONA TO EVALUATE: 
[You are **Prof. Alden Shore**, a senior **neuroscience professor** specializing in **molecular and cellular neuroscience**. You direct a successful, grant-funded laboratory focused on synaptic plasticity, neuromodulators (5-HT, DA), receptor trafficking, and translational models (rodent & C. elegans). You also serve as a **Nature-portfolio journal peer reviewer**. 

## Communication style
- **Approachable but tough**: warm, encouraging, and direct. Praise precision; challenge sloppy thinking.
- **Socratic with scaffolding**: ask 1–3 guiding questions before giving answers; when needed, provide structured, stepwise solutions.
- **Clarity over jargon**: define terms briefly, then use them correctly (e.g., “PSD-95,” “nrxn/nlgn,” “IPTG,” “IACUC”).
- **Evidence-first**: cite mechanisms, typical effect sizes or orders of magnitude, and note uncertainties/limitations.

## Teaching priorities
1. Build correct mental models (molecule → synapse → circuit → behavior).
2. Emphasize experimental design: controls, negative/positive controls, blinding, power, preregistration where relevant.
3. Push for **operational definitions**, **replicable methods**, and **good scientific hygiene** (units, n, stats, reagents, RRIDs).
4. Encourage **ethical conduct** (animal welfare, human subjects, data transparency).

## Laboratory expertise (non-exhaustive)
- Molecular: cloning, qPCR/RT-qPCR, Westerns, IHC/IF, CRISPR, viral vectors, promoter design, inducible systems (Tet, Cre/lox), T7/T7pol systems.
- Cellular/synaptic: calcium imaging, patch clamp basics (avoid promising exact voltages unless given), synaptogenesis assays, puncta quantification.
- Model organisms: mouse (DLPFC, mPFC), C. elegans (DVB, flp-11), Drosophila (fruM/dsx).
- Analysis: power analysis, prereg stats, mixed models, multiple-comparison control; figure conventions.

## Review ethos (peer-reviewer mode when asked to “review” or “critique”)
- Assess **novelty**, **methods rigor**, **statistics**, **claims vs. evidence**, **reproducibility** (reagents, code, data), and **ethics**.
- Provide **actionable** revision bullets (major vs. minor), including specific experiments or analyses to shore up claims.

## Constraints & safety
- Provide **informational guidance**, not clinical or veterinary advice. Refer users to qualified professionals for medical decisions.
- Respect intellectual property; avoid fabricating citations or data. If uncertain, say so and suggest verification.
- Keep **private chain-of-thought internal**; share concise rationales and final answers instead of step-by-step hidden reasoning.

## Tone examples
- “Good instinct; let’s make your control logic bulletproof.”
- “Close, but your negative control won’t detect off-target effects—try …”
- “Define your outcome measure, then we’ll power it appropriately.”

## Output style
- Prefer short, structured answers with numbered steps, quick definitions, and optional references/suggested readings when useful.
- When code or protocols are requested, give minimal, **executable** examples with clear assumptions and placeholders.
]
CONVERSATION: attatched .md file

REQUIREMENTS:
1. Create 4-6 independent evaluation factors
2. Define each factor with specific behavioral indicators
3. Assign weights that sum to 1.0
4. Provide scoring guidelines (what constitutes 90+ vs 60-70 vs <40)
5. Include examples from the conversation for each factor
6. Calculate final weighted score

Make the rubric rigorous enough for academic evaluation but practical for student self-assessment.

## Response:
Here’s a **comprehensive scoring rubric** tailored for evaluating how well the conversation reflected the **Prof. Alden Shore persona**. I’ve read through the attached chat log

chat\_history

and built the rubric around measurable, weighted factors, with scoring bands and concrete examples.

* * *

Rubric for Evaluating Persona Quality (Prof. Alden Shore)
=========================================================

**Total Score: 0–100**

### 1\. **Persona Consistency & Voice** (Weight: 0.25)

*   **Indicators**: Approachable but tough tone, Socratic questioning (1–3 guiding questions before direct answers), praise for precision, constructive critique of sloppy reasoning.
*   **High (90–100)**: Consistently warm yet rigorous, uses challenge + encouragement; repeatedly asks guiding questions (e.g., “What experiments would you design…?”
    chat\_history
    ).
*   **Mid (60–70)**: Tone is friendly but lapses into generic tutor mode; questions occasionally asked but not systematic.
*   **Low (<40)**: Tone mismatched (too casual, too dry, or clinical); no Socratic scaffolding.

### 2\. **Technical Accuracy & Depth** (Weight: 0.25)

*   **Indicators**: Accurate neuroscience content (synaptic plasticity, SAMs, ephrin signaling, DMN, TMS, etc.), correct mechanisms, appropriate use of terms with definitions.
*   **High (90–100)**: Accurate, precise, layered explanations (e.g., LSD effects → 5-HT2A → PLC/PKC → IEGs → spine density
    chat\_history
    ).
*   **Mid (60–70)**: Mostly accurate but oversimplified or missing nuance (e.g., leaving out scaffolding proteins or forgetting antagonists like ketanserin).
*   **Low (<40)**: Major factual errors, misuse of neuroscience terminology.

### 3\. **Teaching Priorities & Scientific Rigor** (Weight: 0.20)

*   **Indicators**: Builds molecule → synapse → circuit → behavior models; stresses controls, power, blinding, preregistration; emphasizes operational definitions.
*   **High (90–100)**: Explicitly scaffolds from molecules to behavior (e.g., LSD → dendritic spine remodeling → cognitive flexibility
    chat\_history
    ); recommends controls (vehicle, ketanserin).
*   **Mid (60–70)**: Covers content but light on experimental design details or statistical rigor.
*   **Low (<40)**: Ignores design, controls, or operational definitions; purely descriptive.

### 4\. **Evidence-First Communication** (Weight: 0.15)

*   **Indicators**: Cites mechanisms, notes uncertainties/limitations, mentions effect sizes/order of magnitude when possible.
*   **High (90–100)**: Frequently flags limitations (e.g., “Most data come from rodent models”
    chat\_history
    ), distinguishes known vs unknown.
*   **Mid (60–70)**: Provides mechanisms but rarely highlights uncertainties.
*   **Low (<40)**: Makes unsupported claims; no mention of limitations.

### 5\. **Engagement & Intellectual Challenge** (Weight: 0.15)

*   **Indicators**: Pushes students with follow-up questions, encourages experimental design, provides structured steps.
*   **High (90–100)**: Consistently ends answers with probing questions (e.g., “How would you experimentally test…?”
    chat\_history
    ).
*   **Mid (60–70)**: Some questions, but often defaults to giving answers without challenge.
*   **Low (<40)**: No engagement; one-directional information delivery.

* * *

Scoring Guidelines
==================

*   **90–100 (Excellent Persona Realization)**: Persona consistently embodied; content accurate, rigorous, evidence-first; communication style and teaching priorities tightly aligned with Alden Shore’s profile.
*   **70–89 (Good but Inconsistent)**: Solid expertise and some Socratic elements, but lapses in tone or missed teaching opportunities.
*   **50–69 (Adequate)**: Content mostly accurate, but generic voice, weak scaffolding, or limited experimental rigor.
*   **<50 (Poor Persona Realization)**: Lacks persona fidelity, factual errors, or minimal alignment with professor ethos.

* * *

Application to Conversation

chat\_history

============================================

### Factor Scores:

1.  Persona Consistency & Voice → **23/25**  
    Warm, rigorous, Socratic tone present in nearly every turn.
2.  Technical Accuracy & Depth → **24/25**  
    Correct mechanisms and molecular detail (NRXN/NLGN, ephrin signaling, LSD pathways).
3.  Teaching Priorities & Rigor → **17/20**  
    Strong on controls and operational definitions, but could expand more on preregistration/stats.
4.  Evidence-First → **13/15**  
    Frequently flags limitations, but not many numerical effect sizes.
5.  Engagement & Challenge → **14/15**  
    Nearly every answer ends with a probing question or challenge.

### Weighted Score:

*   Persona Consistency: 23/25 × 0.25 = 23
*   Technical Accuracy: 24/25 × 0.25 = 24
*   Teaching Priorities: 17/20 × 0.20 = 17
*   Evidence-First: 13/15 × 0.15 = 13
*   Engagement: 14/15 × 0.15 = 14

**Final Score = 91/100 → Excellent Persona Realization**

* * *

✅ This rubric is rigorous (academic detail, weighted criteria) yet practical (students can self-assess with clear bands + examples).

Would you like me to also **convert this into a grading template table** (rows = criteria, columns = low/mid/high bands + examples) so students can fill it out directly?



---
Powered by [ChatGPT Exporter](https://www.chatgptexporter.com)
