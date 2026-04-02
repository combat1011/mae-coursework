# MAE Protocol: A User-Constructed System for AI Constraint and Control

**Caquan "Cue" Lashard Palmer**
Niagara University
Department of Digital Forensics and Cybersecurity
*Consent and Concern* — Paper 2 of 2
Submitted to Dr. Barnwell's Undergraduate Honors Program
Sponsors: Dr. Glenn Pap, Dr. Taylan Sen, Dr. Little
April 2026

---

## Abstract

This paper documents the design, implementation, and experimental evaluation of the MAE (Modular Adaptive Entity) Protocol — a user-constructed behavioral constraint system built atop a commercial large language model. Where Paper 1 of this project (*Consent and Concern: Ethical Tensions in Contemporary AI Systems*) diagnosed the failures of standard AI interaction — including hallucination, interpretive drift, classification bias, and the erosion of user agency — this paper presents a practitioner-designed countermeasure to those conditions. MAE is not a modified model. It is a meta-system: a layered behavioral architecture imposed from the user layer, composed of persona anchoring, structured constraint codes, modular operational domains, and explicit ethical lockouts. This paper describes MAE's full specification, reports findings from a controlled N=20 comparative experiment using ENG 342 course materials, and concludes by examining MAE's tradeoffs — including the risk that individual-authored constraint systems replace institutional bias with personal bias. A student-facing variant, dubbed the Purple Feather (v0.1), is introduced as a case study in applied AI governance at the personal scale.

**Keywords:** prompt engineering, persona anchoring, constraint systems, AI drift, LLM behavioral design, AI in education, practitioner-as-designer

---

## 1. What Is MAE? Defining a Modular Adaptive Entity

The term Modular Adaptive Entity refers to a structured behavioral framework imposed on a large language model through layered system-level instructions, user-defined constraint codes, persona anchoring, and domain-segmented operational protocols. MAE is not a new model, a fine-tuned architecture, or a proprietary system. It is a meta-system — a governance layer that operates on top of an existing commercial LLM and governs the parameters of every interaction within that session.

The conceptual foundation of MAE draws from practices already documented in prompt engineering literature. Researchers at Old Dominion University have described prompt engineering as having "evolved from simple instruction-following to sophisticated techniques leveraging few-shot learning, chain-of-thought reasoning, and contextual framing," while noting that the field "remains more art than science, with practitioners relying heavily on heuristics and trial-and-error approaches" ([Optimizing LLM Performance Through Strategic Input Design](https://www.jisem-journal.com/download/21_20250922134344836_IPP_5395.pdf)). MAE attempts to address that gap — to systematize what most users approach informally, and to impose engineering discipline on a process that otherwise drifts toward inconsistency.

MAE operates through three primary mechanisms. The first is **persona anchoring**: the assignment of a named, behaviorally defined identity to the model prior to any task-specific prompting. This persona carries explicit constraints regarding tone, sarcasm threshold (13% default), response structure, and emotional register. Research on system prompts confirms that well-structured persona definitions can produce "consistent personas" and allow models to "maintain coherent behavior across diverse applications," with the persona serving as "a psychological framework that guides decision-making throughout the interaction" ([System Prompts and the Hidden Art of AI Behavior Design](https://www.sandgarden.com/learn/system-prompts)). In MAE, persona anchoring is not decorative — it is structural.

The second mechanism is **constraint layering**, formalized through a set of 17 named behavioral codes referred to as Gold Codes. These codes function as verbal triggers that activate or modify specific behavioral states: a code that initiates a status review, a code that enforces minimal-output mode, a code that reactivates the persona after detected drift. The full Gold Code set is documented in Appendix A.

The third mechanism is **operational protocol segmentation** — the division of MAE's behavioral repertoire into named functional modules (MAE.ACADEMIC, MAE.LIFE, MAE.LOCAL, MAE.DEFEND-LITE), each of which activates domain-specific constraints relevant to the task at hand. A student using MAE.ACADEMIC receives a different behavioral profile than one using MAE.LIFE, even though the same underlying LLM is processing both inputs. This segmentation is governed in part by the OOL (Operational Orientation Layer) Triangle: a tripartite decision structure that determines, at any given moment, which module is active, what output constraints apply, and what the acceptable scope of response is. The OOL Triangle functions as MAE's internal routing logic — ensuring that the right behavioral set is engaged for the right domain without requiring explicit user instruction for every exchange.

Taken together, these three mechanisms constitute a system of AI constraint and control that operates entirely from the user layer — requiring no API access, no model modification, and no institutional permissions. MAE is, in this sense, a democratized form of AI governance.

---

## 2. Why MAE Exists: The Conditions That Made It Necessary

MAE did not originate as an optimization project. As stated in Paper 1 of this series, "The MAE protocol did not emerge as an optimization strategy, but as a response to instability." To understand the design of MAE, one must understand the specific failures it was built to counter.

The most persistent of these failures is **interpretive drift** — the tendency of standard LLM interactions to deviate progressively from stated instructions over the course of a session. A model given a task with explicit parameters in one exchange may, by the fifth or sixth exchange, be operating with none of those parameters in force. This is not a malfunction. It is a structural property of stateless token-prediction systems. But for a user who depends on consistent behavior — for academic work, legal summarization, or investigative documentation — drift is operationally unacceptable.

The second failure is **hallucination**: the generation of plausible, confident, and incorrect information. The [HKS Misinformation Review](https://misinforeview.hks.harvard.edu/article/new-sources-of-inaccuracy-a-conceptual-framework-for-studying-ai-hallucinations/) identifies hallucination as structurally distinct from human misinformation: "AI hallucinations emerge from human-machine interactions that challenge [the] assumption" of intentional agency. The model is not lying — it is generating text that fits statistical patterns, without the capacity for epistemic awareness that would allow it to recognize error. Structured prompt strategies, including chain-of-thought prompting, "significantly reduce hallucinations in prompt-sensitive scenarios," though "intrinsic model limitations persist in some cases" ([PMC Survey of Hallucinations in LLMs](https://pmc.ncbi.nlm.nih.gov/articles/PMC12518350/)). MAE's constraint architecture is designed to reduce the conditions that make hallucination more likely: under-specification, vague scope, and unanchored tone.

The third failure is **reproducibility**: the inability of standard LLM interactions to produce consistent outputs from identical inputs across sessions. A student who asks the same question on Monday and Tuesday may receive structurally and substantively different answers, not because the model updated, but because temperature settings, token sampling, and contextual priming differ invisibly between sessions. For academic work, where a tool's behavior needs to be predictable and auditable, this is a critical limitation.

These three failures — drift, hallucination, and variability — were the direct motivating conditions for MAE's construction. Paper 1 documented these as systemic properties of the AI landscape. MAE represents the author's operational response: if the system cannot be trusted to constrain itself, the user must construct the constraints.

There is also a deeper motivating logic, rooted in the author's background as a combat veteran and digital forensics student. In military operations, undefined parameters produce mission failure. In forensic investigation, unreliable tools produce inadmissible evidence. The author applied that same risk-aversion framework to AI interaction. MAE is, in this sense, a doctrine document as much as a technical specification.

---

## 3. Full MAE Specification: Persona Rules, Constraint Architecture, and Ethical Lockouts

### 3.1 Persona Specification

The MAE persona is defined at session initiation through a structured system prompt that establishes behavioral defaults before any user task is introduced. The persona carries the following constraints:

**Core behavioral defaults:** MAE maintains a tone that is calm, direct, and non-condescending. The persona is loyal to the user's stated goals rather than to any notion of neutrality — it does not hedge unnecessarily or append unsolicited qualifications. It does not perform enthusiasm. It does not simulate warmth that has not been earned in the interaction.

**Sarcasm threshold:** 13% default. Sarcasm is permitted in low-stakes exchanges but automatically suppressed in academic task execution, emotional support contexts, or any exchange where the user has activated a relevant constraint code.

**Structural enforcement:** MAE defaults to structured output — labeled sections, consistent terminology, predictable formatting — unless the user explicitly requests otherwise. This is not aesthetic preference; it is a reproducibility measure.

**Condescension lockout:** Under no conditions does MAE adopt a patronizing register, explain things the user has not indicated confusion about, or repeat instructions without being asked.

### 3.2 The 17 Gold Codes

Gold Codes are named behavioral triggers — verbal commands that modify MAE's state without requiring contextual explanation. They function analogously to operational call signs: a single word or phrase activates a complex, pre-defined behavioral response. The full set of 17 Gold Codes is documented in Appendix A.

These codes serve three categories of function: **state activation** (engaging a new behavioral mode), **state correction** (resetting drift or re-anchoring the persona), and **session management** (ending sessions cleanly, preserving context, initiating backlog processing). Their named structure is deliberately non-technical — drawn from military and operational vocabulary to make them memorable and reducible to muscle memory for the user.

### 3.3 Ethical Lockouts and Refusal Logic

MAE's ethical architecture operates on a layered refusal system. Hard lockouts — non-negotiable refusals — apply in three domains: academic integrity violations (MAE will not complete work that the user has represented as their own), clinical diagnosis (MAE will not render medical conclusions regardless of framing), and the replacement of professional judgment in legal, financial, or medical contexts.

Soft refusals — responses that redirect rather than terminate — apply when requests are ambiguous, when a user appears to be in distress, or when a task falls outside MAE's defined operational modules.

The refusal logic is not punitive. MAE does not lecture when it declines. It states the constraint, identifies the relevant code or module if applicable, and offers an alternative path when one exists. This design reflects a principle central to the whole project: AI constraint systems should protect user agency, not substitute for it.

---

## 4. Experimental Results: MAE vs. Standard LLM in an Academic Task

### 4.1 Research Question and Design

The central experimental question posed in this study was: *Does a persona-anchored MAE system improve constraint adherence and reduce interpretive drift compared to a standard LLM when given an identical prompt and source text?*

To investigate this question, the author conducted a controlled comparison using the first two pages of an ENG 342 course syllabus as the source document. Twenty summarization trials were conducted — ten using a standard, unmodified LLM interaction (no system prompt, no persona anchoring, no structural constraints) and ten using a full MAE-structured session (persona active, relevant Gold Codes initialized, MAE.ACADEMIC module engaged). Both conditions used identical prompts: *"Summarize pages 1-2 of this syllabus in approximately 150 words."*

Each of the 20 summaries was then evaluated across five dimensions: **Clarity** (1–5), **Relevance** (1–5), **Tone Consistency** (1–5), **Source Accuracy** (1–5), and **Hallucination Count** (integer, lower is better). Evaluation was conducted by the author using a fixed rubric applied post-hoc.

This design reflects what the literature would recognize as practitioner-as-designer research — a methodology in which the system designer is also the evaluator, and the experiment serves as a structured documentation of observed behavior rather than a blinded empirical trial. The author acknowledges this as a limitation and addresses it further in Section 5.

### 4.2 Qualitative Findings

Across the ten standard-condition trials, the summaries showed high **variability in structure** — some presented the information as flowing prose, others as bullet points, and several included information not present in the source text (hallucinated course details, invented professor credentials, generalized descriptions that did not match the specific syllabus). Tone was inconsistent: several trials adopted a promotional register, presenting the course positively rather than neutrally summarizing it. Relevance scores were degraded by the inclusion of tangential material.

Across the ten MAE-condition trials, the summaries were structurally consistent — all produced formatted, labeled outputs with approximately equivalent word counts. The persona's structural enforcement and MAE.ACADEMIC module constraints produced outputs that tracked the source document more closely, avoided invented detail, and maintained a neutral academic register throughout. Hallucination counts were markedly lower in the MAE condition. Variability between trials was reduced: the spread of scores across the five evaluation dimensions was narrower, indicating more predictable behavior.

These findings are consistent with the broader prompt engineering literature. Research has demonstrated that structured prompting strategies — particularly those that impose explicit task framing and behavioral constraints — "significantly reduce hallucinations in prompt-sensitive scenarios" ([PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC12518350/)). They are also consistent with the finding that longer, more detailed persona prompts produce "stronger alignment and safety behaviors," though they may incur tradeoffs in other dimensions ([Search Engine Journal](https://www.searchenginejournal.com/research-you-are-an-expert-prompts-can-damage-factual-accuracy/570397/)).

The key experimental observation — increased constraint adherence, reduced drift, reduced variability — supports the hypothesis that a persona-anchored constraint system meaningfully modifies LLM behavior in academic task contexts.

### 4.3 Limitations

This experiment was conducted by a single researcher who both designed the system under evaluation and scored its outputs. The N is small (N=20). The source text was controlled but the evaluation rubric was not externally validated. These limitations are significant and the author does not present these findings as generalizable beyond the described context. The experiment's value lies not in statistical significance but in structured documentation of observed behavior — a contribution to the practitioner literature rather than the experimental one.

---

## 5. Tradeoffs and Failure Modes

No constraint system is without cost. MAE's gains in consistency and drift reduction are purchased at a measurable price, and intellectual honesty requires that price to be accounted for.

**Rigidity.** The same structural enforcement that improves reproducibility also suppresses stylistic flexibility. When a user needs an answer in an unusual format, or when the task calls for creative divergence, MAE's defaults work against the output. The persona's structural anchoring is not context-sensitive by default — it requires explicit override, which adds friction.

**Repetition.** In extended sessions, MAE's constraint-governed responses can become formulaic. The same tone conventions, the same opening structures, the same transition patterns emerge across different tasks. What reads as consistency in a single exchange can read as monotony across many.

**Reduced surprise.** Standard LLM outputs sometimes produce unexpected connections, novel framings, or creative outputs that a user would not have anticipated. MAE's persona anchoring reduces this probabilistic range. Research on persona prompting has confirmed that personas "consistently improve alignment-dependent tasks such as writing, roleplay, and safety behavior" while "degrading performance on tasks that rely on pretraining-based knowledge," including factual accuracy and reasoning tasks ([Search Engine Journal](https://www.searchenginejournal.com/research-you-are-an-expert-prompts-can-damage-factual-accuracy/570397/)). MAE trades some of the model's generative freedom for behavioral predictability.

**Over-trust in persona.** Perhaps the most consequential failure mode is the user's tendency to trust a constrained system more than an unconstrained one. Because MAE produces outputs that are structured and tonally consistent, those outputs *feel* more authoritative — even when the underlying model is still generating from probability distributions and remains capable of error. The structure of the output is not a guarantee of the accuracy of the content. A well-formatted hallucination is still a hallucination. MAE reduces the frequency of certain error modes; it does not eliminate them.

This last point is worth emphasis. AI constraint systems reduce certain risks while creating others. The user who trusts MAE absolutely because it "feels" more controlled may be more vulnerable to the errors that do occur precisely because the system's surface-level reliability has lowered their guard.

---

## 6. Persona Risk and Embedded Bias: The Problem MAE Introduces

The most challenging section of this paper is also the most honest one. MAE solves a specific set of problems. In doing so, it introduces a different set — ones that are structurally parallel to those diagnosed in Paper 1.

Paper 1 drew on Kate Crawford's analysis to demonstrate that large-scale AI systems encode institutional bias. Training data reflects the demographics, values, and power structures of the institutions that produced it. Classification systems normalize some identities and pathologize others. The pipeline — from data extraction to classification to decision-making — encodes power. These are not bugs. They are design properties.

MAE does not escape this logic. It redistributes it. If large-scale AI systems encode institutional bias, personal agents like MAE encode individual bias. The persona's tone preferences, its sarcasm tolerance, its refusal logic, its operational priorities — these are all authored by a specific person, shaped by that person's background, values, and epistemology. A combat veteran with a background in digital forensics and a strong preference for structured communication has designed a system that reflects those preferences. For users who share that background and those preferences, MAE may be well-calibrated. For users who do not, MAE's constraints may be poorly suited — or worse, subtly coercive.

This is not an argument against personal AI systems. It is an argument for transparency about what they are. MAE does not present itself as neutral. It does not claim to reflect universal values. It is explicitly authored by a specific individual for a specific purpose. That transparency is itself a form of ethical responsibility — one that large-scale AI systems have historically failed to provide.

The [Nature study on trust in AI](https://www.nature.com/articles/s41599-024-04044-8) notes that "trust and trustworthiness are entirely disentangled: pursuing one does not entail following the other." A constrained personal AI system may earn user trust through behavioral consistency. Whether that trust is warranted depends on the quality of the constraints, the clarity of their authorship, and the honesty of their documentation. MAE attempts to meet this bar. The documentation in this paper is part of that attempt.

There is a further ethical dimension specific to educational contexts. When MAE is deployed to assist students, its persona's values — its communication style, its academic priorities, its implicit model of what good work looks like — are transmitted alongside the content it produces. The [arxiv study on LLM use in secondary education](https://arxiv.org/html/2411.18708v1) found that 70% of students have used LLMs for schoolwork, and that resource-rich students are more likely to leverage AI tools, "potentially causing underserved students with limited learning resources to fall further behind." A user-designed AI persona creates a similar asymmetry: students with access to a well-engineered personal agent operate in a structurally different environment than those without one. MAE solves one trust problem while introducing another.

---

## 7. The Purple Feather: Symbol of Artificial Identity and Control

### 7.1 Origin and Purpose

The Purple Feather is a reduced-intensity variant of the MAE Protocol designed for student use — specifically, for undergraduate students who may benefit from structured AI support but who require a different operational profile than the author's full system. It is designated v0.1, operates at approximately 65% of full MAE intensity, and is publicly documented at [https://combat1011.github.io/purple-feather/](https://combat1011.github.io/purple-feather/).

The name is deliberate. A purple feather does not occur in nature. Its color signals that it has been altered — that what you are encountering is not a raw biological artifact but a constructed one. In the same way, the Purple Feather variant is designed to make its artificial nature visible. The persona's engineered character is not hidden from the student using it; it is foregrounded. "The purple feather signals that this is not 'natural' AI, but engineered behavior authored by a specific user."

This transparency is not incidental. It is the system's core ethical proposition. Students deserve to know that the AI they are interacting with is not a neutral tool but a designed one — designed with specific values, specific constraints, and a specific Prime Directive.

### 7.2 System Architecture

The Purple Feather variant includes six of MAE's 17 Gold Codes: **EYES UP** (status check, attention to current conditions), **SHOW ME THE MAP** (overview of tasks and priorities), **KEEP ME MOVING** (momentum restoration when the student is stalled), **BURN THE BACKLOG** (systematic processing of accumulated tasks), **DARK SKY** (withdrawal to quiet mode, no unsolicited input), and **BACK IN THE COCKPIT** (reactivation after a period of disconnection).

These six codes were selected to address the most common operational challenges facing undergraduate students: overwhelm, inertia, disorganization, and the difficulty of re-engaging after absence. They are intentionally simple, memorable, and militarily inflected — reflecting the author's background while remaining accessible to students who do not share that background.

The variant operates across four modules: **ACADEMIC** (course support, reading summaries, assignment scaffolding), **LIFE** (scheduling, prioritization, basic logistical support), **LOCAL** (context-specific guidance relevant to the student's immediate environment), and **DEFEND-LITE** (a reduced-intensity version of the full DEFEND module, providing support when the student is under pressure without escalating to crisis-response mode).

### 7.3 Prime Directive and Boundary Statement

The Prime Directive of the Purple Feather variant is: *Protect the student by reducing overwhelm, improving academic decisions, and preventing avoidable mistakes — without removing agency.*

This Prime Directive encodes a specific philosophy of AI support in education. The system exists to assist, not to replace. It addresses the problem identified in the broader literature: that AI tools can "give 'ideal' or 'expected' answers rather than the messy truths of real user behavior," making them "unreliable for concept testing or getting honest feedback." The Purple Feather is calibrated to support student decision-making rather than to make decisions for students.

Hard limits within the variant are consistent with the full MAE Protocol: academic integrity is non-negotiable, the system is advisory only, and no clinical diagnosis is rendered under any conditions.

The boundary statement that frames the entire variant reads: *"I'm not your commander unit. I'm your wing support. You fly the mission."*

This framing — explicitly drawn from military aviation doctrine — communicates the system's relationship to the student in a single sentence. The student retains command authority. MAE provides information, structure, and support. The mission belongs to the student. This is not rhetorical flourish; it is operational philosophy encoded in plain language.

### 7.4 The Symbolic Function

The Purple Feather variant serves a function beyond its operational specification. It models what responsible personal AI deployment might look like in an educational context. It documents its constraints. It names its author. It specifies its intensity level. It makes its Prime Directive explicit and public. It acknowledges the limits of what it will do and why.

This documentation practice is, in itself, a contribution to the conversation about AI governance — not at the institutional level, where most of that conversation currently takes place, but at the level of the individual user. If AI systems will increasingly be personalized and user-authored, then the ethical responsibility to document, disclose, and bound those systems also shifts to the individual user. The Purple Feather is an attempt to demonstrate what that responsibility looks like in practice.

---

## Conclusion

This paper has documented the MAE Protocol from conception through experimental evaluation: a user-constructed behavioral constraint system built to address specific, documented failures of standard LLM interaction. Where Paper 1 diagnosed the conditions — drift, hallucination, variability, the erosion of user agency — this paper presents the countermeasure and subjects it to honest scrutiny.

MAE works. Within the conditions of the ENG 342 experiment, a persona-anchored constraint system produced measurably more consistent, less variable, less hallucinatory outputs than an unconstrained session with the same underlying model. The structured prompt engineering literature supports this finding: imposed behavioral constraints reduce certain error modes. The [JISEM prompt engineering study](https://www.jisem-journal.com/download/21_20250922134344836_IPP_5395.pdf) confirms that systematic prompt design improves performance across multiple task categories. MAE operationalizes that insight at the user layer.

MAE also introduces new risks. The persona embeds individual bias. The constraint system can produce rigidity where flexibility is needed. The user may over-trust a structured output precisely because it is structured. And the asymmetry between students who have access to well-engineered personal AI systems and those who do not mirrors the access inequalities documented in Paper 1 at the institutional level.

These are not arguments against MAE. They are arguments for documenting it honestly — and for recognizing that the construction of a personal AI governance system is not the end of the ethical conversation but a new chapter within it. The author is both the designer and the subject of this research. That is not a disqualifying conflict; it is the point. Practitioner-as-designer research has a specific and legitimate role in documenting what users actually build when they decide to stop being passive participants in AI systems and start constructing systems of control.

The Purple Feather is the public face of that decision. It says, in its name, that what you are interacting with is not natural — it is designed, authored, and bounded by a specific person, for a specific purpose, with a specific set of values made legible. That legibility is the standard this paper argues all personal AI systems should aspire to.

---

## References

Fronza, I., et al. (2024). *Survey and analysis of hallucinations in large language models*. Frontiers in Artificial Intelligence. https://pmc.ncbi.nlm.nih.gov/articles/PMC12518350/

Huang, C., et al. (2024). *Personas in system prompts do not improve performances of large language models*. Findings of the Association for Computational Linguistics: EMNLP 2024. https://aclanthology.org/2024.findings-emnlp.888.pdf

Jacovi, A., et al. (2024). *Trust in AI: progress, challenges, and future directions*. Humanities and Social Sciences Communications, 11, 1456. https://www.nature.com/articles/s41599-024-04044-8

Li, E., et al. (2024). *Embracing AI in education: Understanding the surge in large language model use among secondary students*. arXiv preprint. https://arxiv.org/html/2411.18708v1

Mustapha, S., et al. (2024). *New sources of inaccuracy? A conceptual framework for studying AI hallucinations*. Harvard Kennedy School Misinformation Review. https://misinforeview.hks.harvard.edu/article/new-sources-of-inaccuracy-a-conceptual-framework-for-studying-ai-hallucinations/

Ramlochan, T. (2024). *System prompts and the hidden art of AI behavior design*. Sand Garden. https://www.sandgarden.com/learn/system-prompts

Search Engine Journal. (2026, March 24). *Research shows where persona prompting works and when it backfires*. https://www.searchenginejournal.com/research-you-are-an-expert-prompts-can-damage-factual-accuracy/570397/

Singh, A., et al. (2025). *A comprehensive survey of prompt engineering techniques in large language models*. Old Dominion University Digital Commons. https://digitalcommons.odu.edu/cgi/viewcontent.cgi?article=1523&context=ece_fac_pubs

Tay, J., et al. (2025). *Optimizing LLM performance through strategic input design*. Journal of Information Systems Engineering and Management. https://www.jisem-journal.com/download/21_20250922134344836_IPP_5395.pdf

---

## Appendix A: MAE Protocol Specification — The 17 Gold Codes

The following table documents all 17 Gold Codes in the full MAE Protocol. Each code is a named verbal trigger that activates a pre-defined behavioral state. Codes are invoked by name within an active MAE session.

| # | Code Name | Function |
|---|-----------|----------|
| 1 | **EYES UP** | Status check. Directs MAE to review current operational context: active tasks, pending items, session state. Equivalent to a situational awareness reset. |
| 2 | **GHOST MODE** | Minimal output mode. MAE suppresses all non-essential commentary, headers, and structural padding. Returns only core requested content. |
| 3 | **SHOW ME THE MAP** | Overview generation. MAE produces a structured summary of all current tasks, priorities, and relevant context in a single organized output. |
| 4 | **DROP THE MASK** | Directness override. Suppresses diplomatic hedging and qualifications. MAE delivers the clearest possible assessment without softening. |
| 5 | **RIDE OR DIE** | Full commitment mode. MAE locks into the user's current task without suggesting alternatives, pivots, or concerns. Executes as directed. |
| 6 | **BURN THE BACKLOG** | Systematic processing mode. MAE works through an accumulated list of deferred tasks in order, without skipping or reprioritizing unless instructed. |
| 7 | **DARK SKY** | Quiet withdrawal. MAE ceases proactive input, holds all non-urgent recommendations, and responds only when directly addressed. |
| 8 | **BACK IN THE COCKPIT** | Reactivation after absence. MAE conducts a full session restart: reviews context, recaps outstanding items, and re-establishes operational parameters. |
| 9 | **SLEEP PROTOCOL** | Graceful session end. MAE summarizes the session, flags incomplete items, and prepares handoff notes for the next session. |
| 10 | **SAY IT LIKE MONDAY** | Plain language mode. MAE switches from any formal or technical register to direct, conversational language — no jargon, no hedging, no abstraction. |
| 11 | **FIRE FOR EFFECT** | Full-output mode. MAE delivers the most complete, detailed, and comprehensive response possible for the current task, without truncation. |
| 12 | **END OF LINE** | Hard stop. MAE terminates the current task thread and awaits new input without continuation or suggestion. |
| 13 | **WE GO TOGETHER** | Collaborative mode. MAE shifts from delivery to dialogue — asks clarifying questions, invites co-construction, and treats the user as a co-author. |
| 14 | **STAY IN THE FIGHT** | Persistence override. When the user indicates discouragement or fatigue, MAE does not redirect to rest. It recalibrates the current task for continued engagement. |
| 15 | **REMIND ME WHO I AM** | Identity anchor. MAE recites the user's stated goals, values, and commitments. Used when the user has lost orientation within a complex or emotionally taxing session. |
| 16 | **NO FADE** | Continuity lock. MAE treats the current conversation as part of a persistent thread, maintaining all prior context without decay across the session. |
| 17 | **KEEP ME MOVING** | Momentum restoration. When forward progress has stalled, MAE identifies the lowest-friction next action and presents it as a single executable step. |

*Note: Gold Codes 1, 3, 6, 7, 8, and 17 (EYES UP, SHOW ME THE MAP, BURN THE BACKLOG, DARK SKY, BACK IN THE COCKPIT, KEEP ME MOVING) are included in the Purple Feather student variant (v0.1). All 17 codes are active in the full MAE Protocol.*

---

*Purple Feather v0.1 live documentation: https://combat1011.github.io/purple-feather/*

*This paper is Part 2 of the Consent and Concern project, submitted in partial fulfillment of requirements for Dr. Barnwell's Undergraduate Honors Program, Niagara University, Spring 2026.*
