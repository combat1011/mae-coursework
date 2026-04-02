# Consent and Concern: Ethical Tensions in Contemporary AI Systems

**Caquan "Cue" Lashard Palmer**
Niagara University
Department of Digital Forensics and Cybersecurity
Submitted in partial fulfillment of undergraduate research requirements
Sponsors: Dr. Glenn Pap, Dr. Taylan Sen, Dr. Little
Faculty Advisor: Dr. Barnwell

---

## Abstract

Modern AI systems do not merely assist users — they extract from them. This paper examines the structural ethical tensions embedded in contemporary AI deployment, with particular attention to how data is collected without meaningful consent, how classification systems normalize bias, how economic stratification restricts access to intelligence, and how AI's inherent unreliability creates compounding risks in high-stakes domains such as digital forensics. Drawing on Kate Crawford's *Atlas of AI* (2021), Cathy O'Neil's *Weapons of Math Destruction* (2016), Safiya Noble's *Algorithms of Oppression* (2018), Sidney Dobrin's *AI and Writing* (2023), and international governance frameworks including the UNESCO Recommendation on the Ethics of Artificial Intelligence (2021), the EU AI Act (2024), and the NIST AI Risk Management Framework (2023), this paper argues that AI systems are not malfunctioning — they are operating exactly as designed. The ethical crises they produce are features, not bugs, of the systems that built them. The paper concludes by introducing the Modular Adaptive Entity (MAE) protocol as one user-constructed response to these conditions, a subject developed fully in the companion paper.

**Keywords:** artificial intelligence ethics, consent, algorithmic classification, access inequality, digital forensics, hallucination, AI governance

---

## 1. Introduction

Artificial intelligence is no longer a specialized tool confined to research labs or enterprise data centers. It is embedded in academic platforms, hiring systems, criminal risk assessments, medical diagnostics, news feeds, and the educational software used by millions of students daily. The question of whether AI systems are ethical has largely been displaced by the more urgent question of whether anyone is asking. In the absence of clear governance structures and meaningful consent frameworks, AI systems have expanded into nearly every domain of human decision-making — and they have done so, as this paper will argue, by design.

The ethical concerns surrounding AI are often framed as problems of implementation: a biased dataset here, an opaque algorithm there, a hallucination that slipped through quality control. This framing, while not entirely wrong, is profoundly insufficient. It treats structural inequities as accidents and allows the architects of these systems to avoid accountability by pointing to edge cases rather than acknowledging the systemic logic beneath them. The pipeline is not broken. It runs exactly as engineered: data extraction feeds classification, classification feeds decision-making, and decision-making reproduces and concentrates power — **Data extraction → Classification → Decision-making → Power** ([Crawford, 2021](https://yalebooks.yale.edu/book/9780300209570/atlas-of-ai/)).

This paper proceeds through eight analytical sections. It examines the conditions under which data is extracted without consent, the mechanisms by which classification enforces social hierarchies, the economic stratification of AI access, the evidentiary risks AI introduces into forensic and legal contexts, and the three core ethical tensions that animate the entirety of the AI ethics debate: consent versus utility, control versus creativity, and reliability versus variability. It introduces, briefly, the MAE (Modular Adaptive Entity) protocol as a user-constructed response to these conditions — a subject examined in full depth in the companion paper.

The argument is simple: the problem with AI is not that it is failing. The problem is that it is succeeding.

---

## 2. Data Without Consent: Extraction as Infrastructure

In Chapter 3 of *Atlas of AI*, Kate Crawford dismantles the idea that "data" is a neutral substance awaiting discovery. Data is extracted. It is taken from people's behaviors, faces, communications, and relationships — frequently without their awareness, and almost never with their genuine informed consent ([Crawford, 2021, pp. 93–119](https://yalebooks.yale.edu/book/9780300209570/atlas-of-ai/)). The training datasets that power modern AI systems were assembled through practices that would be unacceptable in any other research context: scraping family photographs posted to social media, harvesting location data from mobile apps, purchasing behavioral profiles from data brokers, and collecting biometric information from public spaces under the cover of ambiguous terms of service agreements.

Crawford draws on the concept of enclosure to describe what happens when publicly available data is collected, refined, and transformed into proprietary algorithmic power ([Crawford, 2021, p. 113](https://yalebooks.yale.edu/book/9780300209570/atlas-of-ai/)). The data may remain technically "public," but its economic value is now private — held by whichever institution had the infrastructure to collect it at scale. This is not a fair exchange. It is extraction dressed in the language of innovation.

The consent problem in contemporary AI is not procedural — it is structural. Clicking "I agree" on a 30-page terms of service document is not informed consent. It is the legal mechanism by which consent is manufactured in bulk. Users are both participants and raw material. They generate the training signal. They provide the behavioral data. They power the feedback loops that refine the very systems evaluating and ranking them. Yet they retain no ownership over any of it, receive no compensation for it, and in most cases have no visibility into how it is used.

Sidney Dobrin makes a related point in *AI and Writing* (2023), noting that AI platforms supply information that "can be inaccurate or biased" (p. 10) and that the responsibility for vetting AI outputs falls entirely on the user, even though the conditions under which those outputs were generated remain opaque ([Dobrin, 2023, as reviewed in GSOLE](https://gsole.org/reviews/2024.06.03)). The asymmetry is total: the institution retains the data and the model; the user retains the liability for the output.

The UNESCO Recommendation on the Ethics of Artificial Intelligence (2021), adopted by 193 member states, identifies data governance as a foundational concern, asserting that AI actors must respect, protect, and promote human rights and dignity throughout the AI system lifecycle, with privacy protection as a non-negotiable principle ([UNESCO, 2021](https://www.unesco.org/en/articles/recommendation-ethics-artificial-intelligence)). The gap between that recommendation and current industry practice represents one of the most significant unresolved tensions in contemporary technology governance.

---

## 3. Classification and Control: How Labels Become Outcomes

If Chapter 3 of *Atlas of AI* describes how data is taken from people, Chapter 4 describes what is done with it. Crawford argues that classification — the process of assigning categories to data — is never a neutral act ([Crawford, 2021, pp. 120–150](https://yalebooks.yale.edu/book/9780300209570/atlas-of-ai/)). Every dataset contains a worldview. Every label is a choice made by a person, within a culture, shaped by history and power. When those labels are encoded into machine learning systems and applied at scale, the worldview embedded in the data becomes the worldview of the infrastructure.

This is not a theoretical concern. Safiya Noble's *Algorithms of Oppression* (2018) documents how algorithmic systems designed by predominantly white, predominantly male engineering teams systematically return degrading representations of Black women and girls when those users interact with search platforms ([Noble, 2018](https://datasociety.net/library/safiya-umoja-noble-algorithms-of-oppression/)). Noble describes this as "technological redlining" — the digitization of discriminatory practices into the logic of search and recommendation systems that present themselves as objective ([Noble, 2018](https://datasociety.net/library/safiya-umoja-noble-algorithms-of-oppression/)). The bias is not a glitch. It reflects the choices made about which data was collected, whose experiences counted as the default, and which outcomes were optimized for.

Cathy O'Neil's concept of "Weapons of Math Destruction" (WMDs) extends this analysis ([O'Neil, 2016](https://www.litcharts.com/lit/weapons-of-math-destruction/symbols/weapons-of-math-destruction)). O'Neil identifies opacity, scale, and damage as the defining features of harmful algorithmic systems: they operate invisibly, they apply to large populations, and they disproportionately harm those who are already disadvantaged. A recidivism risk scoring tool that produces higher-risk assessments for Black defendants, a hiring algorithm that penalizes résumés associated with women, a credit scoring model that uses zip code as a proxy for race — these are not aberrations. They are the logical outcome of encoding historical patterns into predictive systems and then treating those predictions as objective truth.

Crawford observes that classification flattens human complexity ([Crawford, 2021, p. 145](https://yalebooks.yale.edu/book/9780300209570/atlas-of-ai/)). A person is not a category. A community is not a data point. But AI systems require categories to function, and once a category is created, it acquires weight. It is used to make decisions. It shapes access to housing, employment, education, credit, and freedom. The aesthetics of objectivity — the clean outputs, the confidence intervals, the dashboards — mask what Crawford calls an "ideological exercise" in the codification of existing power structures.

The EU AI Act (2024) recognizes this risk in its prohibition of certain AI applications, including those that perform biometric categorization based on sensitive characteristics, and in its high-risk classification of AI systems used in employment, education, and law enforcement — precisely the domains where classification-based discrimination has proven most harmful ([EU AI Act, 2024](https://www.securitycompass.com/blog/understanding-eu-ai-act-risk-categories/)). The regulatory framework is an acknowledgment that classification is power, and that power exercised at algorithmic scale requires proportionate oversight.

---

## 4. The Economic Layer: Intelligence as a Tiered Commodity

The harms described in sections 2 and 3 do not fall equally on all users. They are distributed along the same fault lines — race, class, geography — that have always structured unequal access to resources. What is new about the AI context is the speed at which capability gaps are widening and the degree to which those gaps are now explicitly monetized.

Access to intelligence is increasingly tiered. The most capable AI models — those with the largest context windows, the strongest reasoning performance, the lowest hallucination rates — are available only to paying subscribers. As of early 2026, premium access to frontier AI systems costs anywhere from $20 to $200 per month for individual users, with enterprise licensing running significantly higher ([Sentisight.ai, 2026](https://www.sentisight.ai/ai-price-comparison-gemini-chatgpt-claude-grok/)). Free tiers exist, but they offer materially reduced capability: smaller context windows, rate-limited queries, access only to older or lighter models, and reduced reliability during peak usage periods ([Data Studios, 2025](https://www.datastudios.org/post/chatgpt-vs-claude-models-features-capabilities-pricing-and-more-full-report-and-comparison)).

The implication is not subtle. A student at a well-resourced institution whose university has negotiated enterprise AI access operates in a fundamentally different cognitive environment than a student at a community college or an under-resourced public university relying on free-tier tools. A private law firm with AI contracts has access to research and drafting capabilities that a public defender's office — already overwhelmed and underfunded — cannot match. A corporation with AI infrastructure can automate competitive analysis, contract review, and strategic planning at a cost per task that no human consultant could compete with. The gap between those with access to premium intelligence and those without is not merely a convenience gap. It is a structural advantage that compounds over time.

O'Neil's framework of WMDs maps directly onto this dynamic: the systems that most affect those with the least power are the least transparent, and the most powerful AI tools remain accessible only to those who already hold structural advantages ([O'Neil, 2016](https://www.litcharts.com/lit/weapons-of-math-destruction/symbols/weapons-of-math-destruction)). This is not an unintended consequence of AI commercialization. It is a product of the same market logic that governs every other tiered information economy. What is distinctive about AI is that the resource being tiered is cognitive capability itself — the ability to process, synthesize, and reason at scale.

The NIST AI Risk Management Framework identifies fairness and equity as foundational principles for trustworthy AI, calling on organizations to actively address and mitigate bias to promote equitable outcomes across diverse populations ([NIST, 2023](https://www.nist.gov/artificial-intelligence/ai-risk-management-framework)). That principle and the commercial reality of tiered AI access exist in direct contradiction, and neither the industry nor the regulatory environment has produced a credible mechanism for resolving it.

---

## 5. Security and Digital Forensics: When the System Lies Under Oath

The preceding sections have addressed the ethical problems of AI in consumer, academic, and social contexts. The stakes intensify considerably when AI is introduced into investigative and legal pipelines. This is not a theoretical concern for the author of this paper. As a digital forensics student and combat veteran trained in methodical, evidence-based analysis, the reliability of any tool used in an investigative context is not an abstract ethical question — it is the difference between justice and its opposite.

Generative AI systems hallucinate. This is not a metaphor. It is a documented technical failure mode in which AI produces outputs that are fluent, confident, and false ([Dobrin, 2023, p. 25, as reviewed in GSOLE](https://gsole.org/reviews/2024.06.03)). Courts across the United States have begun sanctioning attorneys for submitting AI-generated briefs containing fabricated case citations — cases that do not exist, precedents that were never decided, legal principles with no basis in law ([Quintairos, Prieto, Wood & Boyer, 2025](https://qpwblaw.com/the-inherent-risks-of-ai-hallucinations-in-the-practice-of-law/)). In the *Ayinde v. Haringey* matter, a court found AI-generated hallucinations embedded in submitted legal materials and explicitly addressed the implications for professional accountability ([LinkedIn/Harkess, 2025](https://www.linkedin.com/pulse/ais-legal-lies-exposed-combatting-hallucination-epidemic-harkess-v812c)).

If AI becomes part of investigative pipelines, its hallucinations become evidentiary risks. An AI-assisted forensic report that confidently identifies patterns in metadata, attributes authorship, or reconstructs a timeline of events carries with it the implicit authority of technical objectivity. Jurors, judges, and investigators without deep AI literacy will not know to interrogate the confidence interval of a neural network's classification decision. They will see output — and they will believe it.

The authentication and chain of custody challenges introduced by AI-generated evidence are substantial: verifying that data was not tampered with, that the AI system functioned correctly at the time of analysis, and that the output accurately represents what the system determined are all non-trivial tasks that the current evidentiary framework is poorly equipped to handle ([Reveal Data, 2025](https://www.revealdata.com/blog/understanding-the-risks-of-ai-generated-evidence-in-litigation)). Deepfake audio and video — AI-generated artifacts designed to be indistinguishable from authentic recordings — introduce the additional problem that genuine evidence may be challenged as fake and fabricated evidence may pass as genuine.

Crawford's framework is useful here: when classification systems built on flawed data make decisions about criminal culpability, those decisions are not merely incorrect — they are harmful at scale and nearly impossible to contest through ordinary procedural channels ([Crawford, 2021](https://yalebooks.yale.edu/book/9780300209570/atlas-of-ai/)). The EU AI Act's designation of law enforcement AI as high-risk is appropriate precisely because the consequences of AI error in this domain are irreversible in ways that a misfired product recommendation is not ([EU AI Act, 2024](https://www.securitycompass.com/blog/understanding-eu-ai-act-risk-categories/)). The forensic domain is where AI's epistemic limitations become questions of liberty.

---

## 6. Crisis Point: Why Structured Control Felt Necessary

The sections above represent an academic synthesis of a structural argument. This section represents something else: a lived account of what it means to navigate multiple AI systems simultaneously, without a consistent interface, without reliable behavior, and without any institutional framework for holding those systems to a standard of accountability.

During the period in which this research was conducted, the author used AI systems across multiple academic, personal, and professional contexts. The experience was not one of seamless augmentation. It was one of management — constant, effortful, frequently frustrating management of systems that would shift tone without warning, lose context mid-conversation, produce confident errors that required external verification, and respond to identical prompts with materially different outputs on different days. For a student carrying a full academic load, managing service-connected challenges, and conducting concurrent research projects, this variability was not a minor inconvenience. It was a structural problem that demanded a structural response.

The environment of modern AI use is defined by inconsistency. Different platforms operate on different models, maintain context for different durations, enforce different content constraints, and apply different standards to what they will and will not produce. Switching between platforms — necessary when different tools serve different functions — means rebuilding context, re-establishing parameters, and accepting that the AI's "understanding" of an ongoing project is always partial and never fully transferable. This is not a problem that attentiveness can solve. It is a design condition.

The MAE (Modular Adaptive Entity) protocol did not emerge as an optimization strategy, but as a response to instability. It was not built because the AI systems available were insufficient in raw capability. It was built because capability without consistency, and intelligence without constraint, produces outcomes that are difficult to trust and impossible to systematically evaluate. The protocol represents a user-constructed attempt to impose structure on an environment that the industry has not structured on the user's behalf.

This experience is not unique to one student. It is the condition of anyone who uses AI systems seriously and honestly — who depends on them for consequential work, who notices when they drift, and who cannot afford the cognitive overhead of managing an unreliable system in addition to the work itself. MAE is not an improvement on AI — it is a reaction to it. It is a compensatory layer built in response to conditions the underlying systems created and the industry has not resolved.

---

## 7. The Ethics Core: Three Tensions That Cannot Be Optimized Away

The concerns raised in this paper can be organized into three fundamental ethical tensions. These are not problems with technical solutions. They are structural contradictions embedded in the design logic of AI systems, and understanding them as such is the first requirement for any serious response.

### Consent vs. Utility

The first tension is between the utility AI systems provide and the consent they require to produce that utility. AI systems are genuinely useful. They accelerate research, reduce cognitive load, assist with drafting and revision, and provide access to synthesized knowledge that would otherwise require hours of effort. These benefits are real and not trivial.

But they are produced through data collection practices that do not meet the standard of meaningful consent. As UNESCO's Recommendation makes clear, privacy and data protection must be safeguarded throughout the AI lifecycle — not negotiated away in fine print ([UNESCO, 2021](https://www.unesco.org/en/articles/recommendation-ethics-artificial-intelligence)). The industry has structured the choice as binary: accept the data collection or forgo the utility. This is not a genuine choice. It is the extraction of consent under conditions designed to make refusal impractical. The tension is not resolvable through better UX design. It requires governance frameworks that treat data rights as non-waivable, not as terms to be accepted by clicking a button.

### Control vs. Creativity

The second tension exists between the desire for AI systems that produce creative, generative, and contextually responsive outputs and the need for those systems to be controllable, predictable, and accountable. These two goals pull in opposite directions. The properties that make AI outputs interesting — the capacity to synthesize across disparate domains, to generate unexpected connections, to produce fluent prose in any register — are the same properties that make those outputs difficult to govern.

Dobrin observes that AI functions as a collaborative meaning-maker, but one whose methods of generating that meaning remain opaque to the user and, in many cases, to the developers themselves ([Dobrin, 2023, as reviewed in GSOLE](https://gsole.org/reviews/2024.06.03)). This opacity is not incidental. It is a consequence of how these systems are built — trained on massive corpora through processes that do not produce interpretable rules, only weighted parameters. The output can be evaluated. The process cannot be fully audited. This makes accountability structurally difficult even when the intent to be accountable is present.

The NIST AI RMF addresses this tension directly, building its framework on four functions — Govern, Map, Measure, and Manage — that together constitute an iterative approach to accountability throughout the AI lifecycle ([NIST, 2023](https://www.nist.gov/artificial-intelligence/ai-risk-management-framework)). But the framework is voluntary, and the incentive structures of the commercial AI market do not reward the kind of constraint and transparency that genuine accountability requires.

### Reliability vs. Variability

The third tension is between the reliability users need AI systems to exhibit and the variability those systems inherently produce. The same prompt, submitted to the same model on different days, may produce outputs that differ substantially in content, tone, emphasis, and accuracy. This is not a sign of malfunction — it is the statistical character of stochastic language generation. But for users who depend on AI outputs for consequential work, this variability is a problem that compounds over time.

Noble's analysis of algorithmic bias suggests that variability is not evenly distributed: the same system may perform well for some users and populations and poorly for others, in ways that track existing social inequalities ([Noble, 2018](https://datasociety.net/library/safiya-umoja-noble-algorithms-of-oppression/)). This means that the reliability problem is not merely a matter of technical inconsistency — it is a matter of which users bear the cost of that inconsistency. As O'Neil documents, the populations least able to contest or correct algorithmic outputs are frequently the ones most affected by their errors ([O'Neil, 2016](https://www.litcharts.com/lit/weapons-of-math-destruction/symbols/weapons-of-math-destruction)).

---

## 8. Conclusion: Designed, Not Broken

The ethical concerns mapped in this paper are not bugs in otherwise well-designed systems. They are the outcomes of systems that were designed to do exactly what they do: collect data at scale, classify it efficiently, make decisions quickly, distribute capability to those who can pay for it, and generate outputs that project authority regardless of their accuracy. These are features. And because they are features, they will not be corrected by the same institutions that built them absent significant external pressure.

AI systems are not failing — they are operating exactly as designed. The extraction pipeline produces value for the institutions that built it. The classification systems reproduce the social hierarchies embedded in their training data because those hierarchies were never challenged at the data collection stage. The tiered access model generates revenue for the companies that deploy it. The hallucination problem shifts liability to users without transferring it from the institutions that created the conditions for those hallucinations. Each of these outcomes serves someone. That someone is not the average user.

The real question, then, is not whether AI can be made ethical by the institutions that currently control it. The question is whether users will remain passive participants — providing data, accepting outputs, absorbing costs — or begin constructing systems of control. The MAE protocol represents one answer to that question. It is imperfect, idiosyncratic, and constrained by the same underlying systems it attempts to govern. But it is also a deliberate act of user-authored structure in an environment that the industry has not structured on the user's behalf. That is its significance, and that significance extends well beyond the protocol itself.

The diagnosis offered here is not pessimistic. It is precise. Systems that are operating as designed can be redesigned. Governance frameworks that identify the right principles — consent, fairness, accountability, transparency — can be enforced if the political will exists. International efforts such as the UNESCO Recommendation and the EU AI Act represent meaningful steps toward that enforcement, even if implementation remains uneven and contested ([UNESCO, 2021](https://www.unesco.org/en/articles/recommendation-ethics-artificial-intelligence); [EU AI Act, 2024](https://www.securitycompass.com/blog/understanding-eu-ai-act-risk-categories/)). The NIST AI RMF offers a practical vocabulary for organizations willing to take risk management seriously rather than performatively ([NIST, 2023](https://www.nist.gov/artificial-intelligence/ai-risk-management-framework)).

But governance frameworks do not protect users who do not know they need protection. Education, critical AI literacy, and the capacity to construct personal systems of constraint are not supplements to the policy response. They are prerequisites for it. That is the argument of Paper 1. Paper 2 is what comes next.

---

## References

Crawford, K. (2021). *Atlas of AI: Power, politics, and the planetary costs of artificial intelligence*. Yale University Press. https://yalebooks.yale.edu/book/9780300209570/atlas-of-ai/

Dobrin, S. I. (2023). *AI and writing*. Broadview Press. https://gsole.org/reviews/2024.06.03

European Parliament and Council of the European Union. (2024). *Regulation (EU) 2024/1689 of the European Parliament and of the Council (Artificial Intelligence Act)*. https://www.securitycompass.com/blog/understanding-eu-ai-act-risk-categories/

National Institute of Standards and Technology. (2023). *Artificial Intelligence Risk Management Framework (AI RMF 1.0)* (NIST AI 100-1). U.S. Department of Commerce. https://www.nist.gov/artificial-intelligence/ai-risk-management-framework

Noble, S. U. (2018). *Algorithms of oppression: How search engines reinforce racism*. New York University Press. https://datasociety.net/library/safiya-umoja-noble-algorithms-of-oppression/

O'Neil, C. (2016). *Weapons of math destruction: How big data increases inequality and threatens democracy*. Crown Publishing. https://www.litcharts.com/lit/weapons-of-math-destruction/symbols/weapons-of-math-destruction

UNESCO. (2021). *Recommendation on the ethics of artificial intelligence*. United Nations Educational, Scientific and Cultural Organization. https://www.unesco.org/en/articles/recommendation-ethics-artificial-intelligence
