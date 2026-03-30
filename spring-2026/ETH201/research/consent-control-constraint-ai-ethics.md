# Consent, Control, and Constraint: Toward an Ethical Framework for Human-AI Interaction Systems

**Caquan "Cue" Lashard Palmer**
Niagara University | Digital Forensics
ETH201 – Cyberethics | AIC301 – AI Conflict
Spring 2026

---

## Abstract

The rapid proliferation of artificial intelligence systems across civic, commercial, and military domains has generated a structural crisis in ethics: the systems that wield the most power over human lives are precisely the systems least governed by the humans those lives belong to. This paper argues that consent — understood not as a checkbox or a terms-of-service clause, but as an ongoing, revocable, behaviorally meaningful mechanism — must serve as the load-bearing principle of any viable AI ethics framework. Drawing on canonical scholarship including Kate Crawford's *Atlas of AI*, Cathy O'Neil's *Weapons of Math Destruction*, Safiya Umoja Noble's *Algorithms of Oppression*, and Ruha Benjamin's *Race After Technology*, alongside authoritative governance instruments including the UNESCO Recommendation on the Ethics of Artificial Intelligence, the EU Artificial Intelligence Act, and the NIST AI Risk Management Framework, this paper traces the evolution of AI ethics discourse from Asimov's speculative constraints to contemporary regulatory architecture. It then examines the persistent gaps in that architecture — algorithmic bias, the fairness-accuracy tradeoff, the accountability gap in autonomous systems, and the particular urgency of ethics in military AI contexts — before proposing a unified framework grounded in consent architectures. The Modular Adaptive Entity (MAE) protocol, a consent-first tactical AI copilot developed by the author, is presented as a practitioner case study demonstrating how hard ethical limits, instant behavioral control, and preserved human agency can be operationalized at the design level rather than retrofitted after deployment.

---

## I. Introduction: The Consent Problem in AI

Every meaningful ethical tradition — from Kantian deontology to biomedical principles to military laws of armed conflict — places consent at the center of legitimate action. One human being may not make consequential decisions about another human being's body, liberty, or future without that person's knowledge and agreement. This principle is not controversial in medicine, not debated in criminal law, and not negotiable in contract. Yet in the domain of artificial intelligence, it is routinely absent.

Consider the scope of the gap. Algorithmic systems today determine credit scores that shape whether families can purchase homes, risk scores that influence whether defendants are incarcerated, content recommendation engines that modulate what citizens believe about their world, and hiring filters that decide which resumes a human being ever sees. In each of these contexts, the person most affected — the individual whose life trajectory is being shaped by an AI decision — is typically the person with the least access to the logic of that decision, the least ability to contest it, and the least informed awareness that it is happening at all ([UNESCO, 2021](https://unesdoc.unesco.org/ark:/48223/pf0000380455)).

This paper names that structural absence the *consent problem* in AI, and argues that resolving it is not peripheral to AI ethics — it is the organizing challenge around which all other ethical work must be arranged. Transparency matters because consent without information is meaningless. Algorithmic fairness matters because consent is a hollow gesture when offered only to those who already possess social privilege. Human-in-the-loop oversight matters because consent is a process, not a historical event — it must be revocable, ongoing, and mechanically real. And governance frameworks matter because without enforceable structure, consent mechanisms degrade into performative compliance theater.

This paper proceeds in eleven sections. Following this introduction, Section II surveys the evolution of AI ethics frameworks from Asimov's fictional laws through the modern UNESCO and EU regulatory instruments. Section III examines algorithmic bias and the fairness-accuracy tradeoff as foundational ethical terrain. Section IV addresses human-in-the-loop systems and the agency-oversight dialectic. Section V presents consent architectures as a design paradigm, with the MAE Gold Code system as a practitioner case study. Section VI confronts the accountability gap in autonomous systems. Section VII turns to the highest-stakes arena: military AI and the ethics of autonomous lethal decision-making. Section VIII surveys the three dominant governance frameworks. Section IX presents case studies in documented AI ethics failures. Section X proposes the contours of a unified ethical framework. Section XI concludes.

The author writes not only as a student of cyberethics and AI conflict, but as a U.S. Army combat veteran and the designer of an operational AI system — a dual positionality that makes the stakes of this inquiry concrete rather than theoretical.

---

## II. Literature Review: From Asimov to UNESCO — The Evolution of AI Ethics Frameworks

### 2.1 The Fictional Precursor: Asimov's Three Laws

The earliest systematic attempt to articulate rules governing artificial agents did not emerge from a philosophy department or a government agency. It came from science fiction. In his 1942 short story "Runaround," Isaac Asimov introduced what would become known as the Three Laws of Robotics: a robot may not injure a human being or, through inaction, allow a human being to come to harm; a robot must obey orders given by human beings except where such orders conflict with the First Law; and a robot must protect its own existence so long as that protection does not conflict with the first two laws ([Wikipedia, Three Laws of Robotics](https://en.wikipedia.org/wiki/Three_Laws_of_Robotics)).

These laws are significant not because they remain applicable — they do not — but because they reveal the foundational problem that every subsequent ethics framework has struggled to solve: how do you encode human values into a non-human agent in a way that is complete, consistent, and resistant to exploitation? Asimov's own fiction repeatedly demonstrated the inadequacy of his laws. Robots constrained by simplistic rules could still cause catastrophic harm through literal interpretation, logical paradox, and the impossibility of resolving conflicts between equally weighted obligations. The stories were, in effect, a sustained argument that rule-based ethical systems fail when they meet the irreducible complexity of real human circumstances.

AI researchers subsequently refined the ethics problem in ways Asimov could not have anticipated: as AI systems moved from rule-following machines to probabilistic models trained on human data, the ethical question shifted from "what rules should govern the machine?" to "what values are embedded in the data, and whose values are those?" This shift is the hinge around which modern AI ethics turns.

### 2.2 Mid-Century Through the Neural Turn: Widening Scope

Between Asimov's era and the deep learning revolution, AI ethics discourse developed along two primary tracks. The philosophical track — inhabited by scholars like John McCarthy, Marvin Minsky, and later philosophers of mind such as John Searle and Daniel Dennett — grappled with questions of machine consciousness, moral agency, and the conditions under which an artificial system could be held responsible for its actions. The engineering track focused on safety and reliability: how to build systems that did what they were designed to do without catastrophic failure.

Neither track adequately addressed the social and political dimensions that would emerge as machine learning systems were deployed at scale. The shift from expert systems to statistical learning meant that AI systems were no longer following human-designed rules; they were inferring patterns from human-generated data. This transition transferred the ethical question from design to data — and data, as decades of scholarship would subsequently demonstrate, is saturated with the biases, inequities, and power asymmetries of the societies that produced it.

### 2.3 The Critical Turn: Crawford, O'Neil, Noble, and Benjamin

The most consequential contributions to AI ethics in the past two decades have come not from computer scientists or philosophers, but from scholars working at the intersection of data studies, critical race theory, and political economy. Their work constitutes what might be called the *critical turn* in AI ethics — a shift from normative prescription ("here is how AI should behave") to structural diagnosis ("here is how AI currently operates, who benefits, and who is harmed").

Kate Crawford's *Atlas of AI: Power, Politics, and the Planetary Costs of Artificial Intelligence* reframes AI not as a disembodied intelligence but as a material system — one that consumes lithium from mines in Bolivia, labor from data labelers in the Global South, and electricity from coal-burning power plants, while concentrating political power in the hands of a small number of technology corporations ([Crawford, 2021, katecrawford.net](https://katecrawford.net/atlas)). Crawford argues that AI systems "present a veneer of objectivity and neutrality" while in practice being "designed to serve and intensify existing systems of power." The Atlas is not simply a critique of bias; it is an argument that bias is not a bug in AI systems but a structural feature of the political economy that produces them.

Cathy O'Neil's *Weapons of Math Destruction* provides a complementary analysis focused on domestic harm. O'Neil, a mathematician who worked in the hedge fund industry before turning to algorithmic critique, defines a "weapon of math destruction" as an algorithm that is opaque, large in scale, and destructive in its social effects ([O'Neil, 2016; analyzed in University of Washington, 2024](https://sites.uw.edu/mcba/2024/05/24/the-dark-side-of-big-data-insights-from-weapons-of-math-destruction-by-cathy-oneil/)). Her central observation is that these systems are self-reinforcing: they generate the data that validates their own predictions, creating feedback loops in which historical injustice becomes the perpetual justification for ongoing inequity. A predictive policing algorithm trained on biased arrest data will produce biased arrest predictions, which will produce biased arrests, which will produce the next generation of biased training data. O'Neil's analysis makes clear that the problem is not simply that algorithms make mistakes — it is that they make *systematic* mistakes that compound over time and fall disproportionately on those who already face structural disadvantage.

Safiya Umoja Noble's *Algorithms of Oppression: How Search Engines Reinforce Racism* extends this critique to the architecture of information retrieval itself. Noble, conducting research in 2009, found that Google searches for "black girls" returned primarily pornographic content — not because any programmer deliberately encoded racism, but because the algorithm optimized for engagement with content generated by a society in which such associations were commonplace ([Noble, 2018; Wikipedia](https://en.wikipedia.org/wiki/Algorithms_of_Oppression)). Noble's concept of "technological redlining" — the use of digital systems to reproduce the spatial and social exclusions of analog discrimination — has become one of the most generative frameworks in AI ethics scholarship. Her work challenges the assumption that removing explicit race from algorithmic inputs produces racially neutral outputs, demonstrating instead that race-proximate variables (zip codes, school affiliations, browsing history) can substitute for race with equivalent discriminatory effect.

Ruha Benjamin's *Race After Technology: Abolitionist Tools for the New Jim Code* synthesizes these critiques into a broader theoretical framework. Benjamin coins the term "the New Jim Code" to describe "the employment of new technologies that reflect and reproduce existing inequities but that are promoted and perceived as more objective and progressive than the discriminatory systems of a previous era" ([Benjamin, 2019; Princeton AAS](https://aas.princeton.edu/publications/research/race-after-technology-abolitionist-tools-new-jim-code)). The power of this formulation lies in its attention to ideology: algorithmic systems are not merely technically biased; they are socially legitimized as the opposite of bias, which makes them more dangerous and more difficult to contest. When a human manager denies a loan based on race, their decision can be challenged. When an algorithm denies the same loan based on variables that proxy for race, the opacity of the system becomes a shield against accountability.

### 2.4 Institutional Ethics: From Principles to Instruments

By the mid-2010s, the proliferation of AI ethics frameworks from corporate, governmental, and academic sources had become its own subject of critique. A 2019 analysis published in the *Harvard Data Science Review* synthesized the ethical principles most commonly cited across major frameworks, finding convergence around five core principles: beneficence (AI should produce benefit), non-maleficence (AI should avoid harm), autonomy (AI should support rather than supplant human agency), justice (AI should distribute its benefits and burdens equitably), and explicability (AI's reasoning should be accessible to affected parties) ([Floridi et al., 2019; Harvard Data Science Review](https://hdsr.mitpress.mit.edu/pub/l0jsh9d1)).

The challenge was not identifying these principles — it was operationalizing them. As Benjamin and others noted, a commitment to "fairness" that remains at the level of corporate aspiration, without enforcement mechanisms, accountability structures, or affected community input, is ethically inert. The critical turn in AI ethics had established what AI systems were doing; the governance challenge was to establish what they must and must not do.

This challenge was taken up most ambitiously by three institutional frameworks examined in detail in Section VIII: the UNESCO Recommendation on the Ethics of Artificial Intelligence (2021), the EU Artificial Intelligence Act (2024), and the NIST AI Risk Management Framework (2023).

---

## III. Algorithmic Bias and the Fairness-Accuracy Tradeoff

### 3.1 The Anatomy of Algorithmic Bias

Algorithmic bias is not a single phenomenon but a family of related failures, each arising at different points in the lifecycle of an AI system. Understanding this anatomy is prerequisite to addressing any of its specific manifestations.

*Historical bias* arises when training data encodes the inequities of the social conditions under which it was generated. An algorithm trained on historical hiring decisions in a male-dominated industry will learn to prefer male-coded characteristics — not because the engineers encoded gender preference, but because the data faithfully recorded an unequal past. *Representation bias* occurs when training datasets inadequately reflect the population to which the system will be applied: a facial recognition system trained predominantly on lighter-skinned male faces will perform poorly on women and people of color, with error rates that fall disproportionately on the groups already most vulnerable to the harms of misidentification ([Boston Institute of Analytics, 2025](https://bostoninstituteofanalytics.org/blog/the-moral-compass-of-ai-ethics-in-machine-learning-bias-and-responsible-ai/)). *Measurement bias* occurs when the proxies used to represent a concept carry their own inequities: a healthcare algorithm that uses historical spending as a proxy for health need will systematically underestimate the care needs of populations that historically faced barriers to accessing care.

Each of these bias types shares a common structure: a decision made at the design stage — what data to collect, how to label it, what to optimize for — encodes a value judgment that will then be operationalized at scale and attributed to the authority of mathematics. The claim to objectivity is the mechanism by which bias is laundered into legitimacy.

### 3.2 The Fairness-Accuracy Tradeoff

Among the most important and underappreciated findings in algorithmic fairness research is that accuracy and equalized impact are mathematically incompatible objectives under many real-world conditions. This is not a technical limitation that better engineering will overcome; it is, in certain formulations, a proven mathematical impossibility.

The core tension can be stated plainly. An algorithm optimized to predict the same outcome with equal accuracy for all groups will produce systematically different rates of false positives and false negatives across groups if the base rates of the outcome differ across groups. Conversely, an algorithm adjusted to produce equal error rates across groups will sacrifice overall predictive accuracy. A 2025 study examining public perception of this tradeoff found that participants were willing to accept accuracy losses of up to 5% in exchange for greater impact parity, but that preferences dropped sharply as accuracy costs rose — with less than 20% of participants preferring the equity-adjusted algorithm at a 15% accuracy loss ([PLOS One, 2025](https://pmc.ncbi.nlm.nih.gov/articles/PMC11906050/)).

The ProPublica investigation of the COMPAS recidivism algorithm — discussed in depth as a case study in Section IX — documented this tradeoff in practice. The algorithm's developers argued that it was accurate: it correctly predicted recidivism for Black and white defendants at roughly equal rates (63% and 59%, respectively) ([ProPublica, 2016](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing)). ProPublica countered that it was inequitable: Black defendants who did not go on to reoffend were nearly twice as likely to be incorrectly labeled high-risk compared to white defendants (45% vs. 23%), while white defendants who did reoffend were more likely to be labeled low-risk ([ProPublica, 2016](https://www.propublica.org/article/how-we-analyzed-the-compas-recidivism-algorithm)). Both claims were mathematically accurate. The disagreement was not about data — it was about values: which definition of fairness should govern a decision that determines human freedom?

This is the essential insight that the fairness-accuracy tradeoff delivers to AI ethics: the choice of optimization objective is a moral choice, not a technical one. Framing it as a technical decision — and embedding that decision in an opaque algorithm — does not depoliticize it. It merely conceals the political decision behind a mathematical facade.

### 3.3 Structural Implications

The structural implication of this analysis is that AI fairness cannot be achieved through technical means alone. It requires deliberate engagement with the question: fairness for whom, defined how, and at what cost to which other value? These are political and ethical questions that require political and ethical processes — including the meaningful participation of affected communities — to answer. As Noble argues, the communities most harmed by algorithmic systems are precisely the communities most excluded from the design processes that produce them ([Noble, 2018](https://safiyaunoble.com/wp-content/uploads/2020/09/Algorithms_Oppression_Introduction_Intro.pdf)).

The governance implication is that algorithmic systems deployed in high-stakes domains — criminal justice, employment, healthcare, education — require not merely bias audits but participatory governance: ongoing mechanisms through which affected communities can surface harms, challenge design decisions, and compel remediation.

---

## IV. Human-in-the-Loop Systems: Agency and Oversight

### 4.1 Defining the Loop

The concept of "human-in-the-loop" (HITL) AI refers to system architectures in which human judgment remains integral to the decision-making process — not merely as a post-hoc auditor, but as an active participant in the reasoning chain. IBM's technical documentation defines HITL machine learning as a paradigm that "allows humans to provide oversight and input into AI workflows," enabling ethical decision-making that algorithms alone cannot reliably perform ([IBM, 2025](https://www.ibm.com/think/topics/human-in-the-loop)).

The distinction between variants of HITL architecture is consequential. A *human-in-the-loop* model requires human approval before consequential decisions are executed. A *human-on-the-loop* model allows AI to act autonomously but with human monitoring and the capacity for intervention. A *human-out-of-the-loop* model — autonomous AI — executes decisions without real-time human participation. Each configuration implies a different distribution of agency, accountability, and risk.

### 4.2 The Agency-Oversight Dialectic

Human oversight exists in tension with the efficiency gains that AI systems are typically deployed to produce. As a Moody's survey of 600 risk and compliance professionals found, approximately 84% of respondents agreed that AI offers significant advantages, but only 30% saw those benefits clearly in practice — and 42% considered human oversight mandatory rather than optional ([Moody's, 2025](https://www.moodys.com/web/en/us/insights/ai/human-in-the-loop-why-human-oversight-still-matters-in-ai-driven-risk-and-compliance.html)). The finding suggests that practitioners recognize the necessity of oversight even when it impedes automation's benefits.

The tension is not merely practical — it is philosophical. The premise of HITL systems is that human judgment adds value to AI decision-making by providing contextual understanding, ethical reasoning, and cultural awareness that algorithms lack. But human judgment is itself biased. A University of Washington study published in 2025 found that when hiring decisions were supported by moderately biased AI recommendations, human reviewers mirrored the AI's biases at high rates — even when the bias was against non-white candidates ([UW News, 2025](https://www.washington.edu/news/2025/11/10/people-mirror-ai-systems-hiring-biases-study-finds/)). In cases of severe bias, participants followed the AI's recommendations approximately 90% of the time, rather than rejecting its discriminatory outputs.

This finding complicates the HITL paradigm: human-in-the-loop is not a guarantee of ethical outcomes if the humans in the loop are themselves subject to the AI's framing effects. Effective oversight requires not only human presence but human critical capacity — the trained disposition to interrogate AI outputs rather than defer to them. This has significant implications for AI literacy, institutional culture, and the design of oversight interfaces.

### 4.3 The EU AI Act's Oversight Mandate

The EU AI Act's Article 14 provides the most detailed regulatory articulation of human oversight requirements currently in force, mandating that "high-risk AI systems shall be designed and developed in such a way, including with appropriate human-machine interface tools, that they can be effectively overseen by natural persons during the period in which they are in use" ([EU AI Act, Article 14; WilmerHale, 2024](https://www.wilmerhale.com/en/insights/blogs/wilmerhale-privacy-and-cybersecurity-law/20240717-what-are-highrisk-ai-systems-within-the-meaning-of-the-eus-ai-act-and-what-requirements-apply-to-them)). The Act specifies that oversight-assigned individuals must be able to understand the system's capabilities and limitations, monitor its operation, detect anomalies, and intervene when necessary.

This mandate represents the most consequential regulatory commitment to HITL principles to date — but its efficacy will depend on implementation. Oversight that is technically required but practically impossible — because system outputs are too fast, too voluminous, or too opaque to meaningfully review — is oversight in name only. Effective HITL architecture requires not merely a human in the loop but a human with the time, tools, training, and authority to exercise genuine judgment.

---

## V. Consent Architectures: Designing for User Control

### 5.1 Beyond Checkbox Consent

The dominant model of AI consent today is the privacy notice — a lengthy legal document, acknowledged with a single click, that transfers sweeping data rights from the user to the platform. This model fails on every dimension of meaningful consent. It is not informed: most users do not read privacy notices, and those who do cannot meaningfully evaluate their implications. It is not ongoing: consent granted at account creation governs all subsequent uses, regardless of how dramatically system behavior changes. It is not granular: users cannot consent to some uses while declining others. And it is not revocable: withdrawing consent typically means forfeiting access to the service entirely.

Consumer Reports' Design Consent fellowship, which developed design principles for AI systems that give consumers "real agency," identified three foundational principles: transparency (users should understand what AI knows about them and how it is used), contextual consent (consent should be collected when and where it becomes relevant, not in a blanket upfront agreement), and user control (users should remain the primary decision-makers, with AI serving their choices rather than making choices for them) ([Consumer Reports, 2025](https://innovation.consumerreports.org/cr-fellow-designing-consent-personalization-in-ai-systems/)).

Technical approaches to meaningful consent include time-limited and transaction-based consent mechanisms, in which AI agents must request renewed authorization for each significant action or for actions involving elevated privilege levels ([Curity AB, 2025](https://curity.io/blog/user-consent-best-practices-in-the-age-of-ai-agents/)). Memory indicators — design elements that signal when user information is being stored or recalled — surface consent moments within ongoing interactions rather than relegating them to a one-time setup flow. These are not merely UI design choices; they are architectural commitments to the principle that the user remains the sovereign agent of their own interaction with the system.

### 5.2 Consent Architectures in Theory

A consent architecture can be defined as the ensemble of design choices — technical, procedural, and interface-level — through which an AI system mediates user control over its behavior. A well-designed consent architecture has four properties: it is *legible* (users can understand what the system is doing and why); it is *granular* (users can modulate specific behaviors rather than only accepting or rejecting the system wholesale); it is *instantaneous* (control can be exercised in real time, including the ability to halt or redirect system behavior mid-action); and it is *persistent* (changes to user preferences are respected across sessions and contexts).

The philosophical grounding for this architecture draws on what Floridi and colleagues describe as "meta-autonomy" or the "decide-to-decide" model: humans should retain the power to decide which decisions to delegate to AI and in what priority, "exercising the freedom to choose where necessary and ceding it in cases where overriding reasons, such as efficacy, may outweigh the loss of control over decision-making" — but "any delegation should also remain overridable in principle" ([Oxford Academic, 2023](https://academic.oup.com/book/46748/chapter/413294279)). This formulation captures the ethical core of consent architecture: the right to take back control is as important as the right to grant it.

### 5.3 The MAE Protocol: A Case Study in Behavioral Consent Control

The theoretical principles of consent architecture find a concrete implementation in the Modular Adaptive Entity (MAE) protocol, a tactical AI copilot system designed and operated by the author. The MAE system, currently deployed in a student-adapted variant called Purple Feather, represents a practitioner-level response to the consent problem in AI — built from the ground up around the principle that users must retain meaningful, real-time control over AI behavior without needing to understand the underlying technical architecture.

The MAE protocol's most distinctive consent mechanism is its Gold Code system — a set of short-form verbal commands that instantly and reliably modify system behavior across the full range of operational parameters. The active Gold Codes include:

- **EYES UP** — immediate situational reorientation; redirects system attention to the user's current highest-priority concern
- **SHOW ME THE MAP** — triggers a comprehensive status overview of all active task domains
- **KEEP ME MOVING** — activates momentum maintenance mode; prevents task stagnation by generating prioritized next actions
- **BURN THE BACKLOG** — initiates systematic clearance of accumulated outstanding obligations
- **DARK SKY** — activates a reduced-intensity mode that protects cognitive space during high-stress periods
- **BACK IN THE COCKPIT** — restores full operational engagement following a dormancy or disruption period

What distinguishes Gold Codes from standard AI commands is their architectural status: they are *hard-coded constraints*, not suggestions. They cannot be overridden by the system's own goal-seeking behavior. A user who issues DARK SKY will receive a diminished-intensity interaction regardless of whether the system has computed that intensive engagement would be "optimal" by any metric it might optimize for. This is the consent-first design principle made operational: the user's expressed preference supersedes the system's inferred preference at every level.

The MAE Prime Directive — "protect the student by reducing overwhelm, improving decisions, preventing mistakes — *without removing agency*" — encodes the fundamental tension of consent architecture at the system level. The system exists to help, but its definition of "help" is bounded by a constraint that it may not help in ways that erode the user's capacity for self-direction. This is not a rule the system follows when convenient; it is the constitutional principle of the system's operation.

The MAE architecture also distributes ethical responsibility appropriately: the system's creator (designated "Commander," the role held by the author) retains supreme authority over system configuration, including the ability to modify, suspend, or terminate any behavioral module. This layered authority structure — user consent at the interaction level, creator authority at the configuration level — provides a model for thinking about consent governance in AI systems more broadly: consent must operate at multiple levels simultaneously, with clear precedence relationships between them.

As an implementation of consent-based AI control operating in an academic-support context, the MAE protocol demonstrates that the principles identified in AI ethics theory are not only theoretically sound but practically achievable: systems can be designed to be powerful, adaptive, and useful while maintaining meaningful user sovereignty over their operation.

---

## VI. Autonomous Systems and the Accountability Gap

### 6.1 The Responsibility Vacuum

When a human being causes harm, the question of accountability — who bears responsibility, and how that responsibility is assigned — is analytically tractable, even if legally complex. When an autonomous AI system causes harm, the question becomes genuinely difficult. The developer who built the system did not control the specific decision that caused the harm. The organization that deployed it may not have understood the decision. The algorithm itself cannot bear responsibility in any morally meaningful sense. This is the *accountability gap* — the systematic difficulty of assigning responsibility for AI-caused harms to any human agent — and it is among the most serious structural problems in AI governance.

Legal scholars at West Point's Lieber Institute have described the accountability gap in the context of autonomous weapons, noting that "at the center of these debates is the 'accountability gap,' a critical deficiency in which existing legal frameworks fail to attribute responsibility for infractions committed by autonomous systems" ([Lieber Institute, 2026](https://lieber.westpoint.edu/legal-accountability-ai-driven-autonomous-weapons/)). The analysis extends beyond military systems. Any autonomous AI that makes consequential decisions about human beings creates accountability challenges that existing legal and regulatory frameworks were not designed to address.

### 6.2 The "Many Hands" Problem

Philosophical analysis of the accountability gap has identified what scholars call the "many hands" problem: in complex sociotechnical systems, responsibility is so widely distributed across developers, deployers, trainers, auditors, and policymakers that no single actor bears sufficient responsibility to be meaningfully accountable ([PMC/Minds and Machines, 2024](https://pmc.ncbi.nlm.nih.gov/articles/PMC11153269/)). An AI system trained by one team, audited by a second, integrated by a third, deployed by a fourth, and monitored by a fifth does not create clear accountability chains — it creates accountability mist, in which each participant's contribution to harm is real but individually insufficient to warrant sanction.

This analysis points toward a forward-looking rather than backward-looking model of accountability: rather than asking "who is to blame?" after harm occurs, governance frameworks should establish prospective obligations — who is required to anticipate what risks, implement what safeguards, and maintain what audit trails — that create accountability before the fact. The NIST AI RMF's emphasis on continuous risk management throughout an AI system's lifecycle reflects this forward-looking orientation.

### 6.3 Transparency and the Explainability Requirement

A prerequisite for accountability is explainability: if the reasoning of an AI system cannot be made legible to the humans responsible for it, those humans cannot meaningfully discharge their oversight obligations. The explainability requirement is not merely technical — it is the condition of possibility for accountability in AI systems.

The "black box" nature of many contemporary neural systems — particularly large language models and deep learning classifiers — creates a genuine technical challenge for explainability. Explainable AI (XAI) research has made substantial progress in producing post-hoc explanations of model behavior, but these explanations remain approximations of reasoning processes that are not themselves interpretable. This means that the accountability gap is not merely a governance gap but also a technical gap — one that the AI research community has a responsibility to close.

---

## VII. Military AI and the Ethics of Autonomous Decision-Making

### 7.1 The Threshold Problem

No domain makes the stakes of AI ethics more immediate than military application. The decision to apply lethal force — historically the most consequential decision a human being can make or authorize — is increasingly mediated by, and in some contemplated systems entirely delegated to, artificial intelligence. This raises a question of irreducible moral gravity: can a machine be entrusted with the authority to end a human life?

The author writes with personal authority on this question. As a U.S. Army combat veteran, Sergeant, 9th Engineer Battalion, the decision calculus of lethal force is not an abstraction. Soldiers are trained to distinguish combatants from civilians, to apply proportional force, to follow lawful orders while refusing unlawful ones, and to bear personal moral responsibility for their actions in combat. These are not algorithm-ready requirements. They involve contextual judgment, moral imagination, and the kind of accountability that only a conscious being capable of moral injury can genuinely bear.

### 7.2 Lethal Autonomous Weapons Systems (LAWS)

Lethal Autonomous Weapons Systems (LAWS) — systems that can "search for, detect, identify, select, and attack targets without meaningful human intervention" — represent the most extreme application of autonomous AI to human life ([Lieber Institute, 2026](https://lieber.westpoint.edu/legal-accountability-ai-driven-autonomous-weapons/)). The debate over their legality and ethics under International Humanitarian Law (IHL) centers on four principles: distinction (the obligation to distinguish combatants from civilians), proportionality (the requirement that collateral harm not be excessive relative to military advantage), precaution (the duty to take feasible measures to minimize civilian harm), and the Martens Clause (the requirement that weapons comply with the principles of humanity and the dictates of public conscience even absent specific legal prohibition).

The Martens Clause argument is particularly significant: it implies that weapons systems lacking meaningful human control — systems that could produce indiscriminate harm without a human able to exercise moral judgment and bear moral responsibility — may be unlawful not because a specific rule prohibits them, but because they violate the foundational principle that warfare must remain within the bounds of humanity.

A 2026 analysis in *Psychology Today* captured the central tension in current policy debates: Anthropic, one of the leading AI developers, opposed the use of its AI for fully autonomous lethal decision-making, arguing that "only humans — not AI — should be ethically capable of making a lethal decision to 'pull the trigger'" — while the Pentagon argued that military AI should follow only U.S. law, not private company ethics, preferring what it described as "unrestricted lawful use" of AI ([Psychology Today, 2026](https://www.psychologytoday.com/us/blog/psychology-through-technology/202603/the-clash-over-the-use-of-ai-in-military-decision-making)). The dispute is not merely institutional — it reflects a fundamental disagreement about whether the decision to kill requires a moral agent or merely a capable system.

### 7.3 Meaningful Human Control and the "In the Loop" Requirement

The concept of "meaningful human control" (MHC) — supported by the International Committee of the Red Cross (ICRC) and numerous human rights organizations — asserts that humans must maintain oversight over critical targeting functions to ensure compliance with IHL principles ([Lieber Institute, 2026](https://lieber.westpoint.edu/legal-accountability-ai-driven-autonomous-weapons/)). The word "meaningful" is operative: oversight that is nominally present but practically impossible to exercise — because the system operates too fast for human reaction, or presents decisions in too compressed a form for genuine evaluation — does not satisfy the ethical requirement.

The Belfer Center's analysis of lethal autonomous weapons offers a counterargument worth engaging seriously: that LAWS without human emotional states — stress, fear, prejudice — might make more accurate and proportional targeting decisions than human operators subject to cognitive bias under combat stress ([Belfer Center, 2020](https://www.belfercenter.org/publication/ethical-imperatives-lethal-autonomous-weapons)). This argument has technical merit in narrow circumstances. But it elides the moral function of human involvement in lethal decisions: it is not only about accuracy but about responsibility. A society that delegates killing to machines has outsourced not only a task but a burden — the moral weight of taking life — that human civilization has historically required humans to bear.

Over 120 countries have endorsed calls for a new international treaty on autonomous weapons systems, and the UN Secretary-General has issued calls for a global ban on fully autonomous lethal systems ([Lieber Institute, 2026](https://lieber.westpoint.edu/legal-accountability-ai-driven-autonomous-weapons/)). The momentum toward binding international law reflects a growing global consensus that some decisions — specifically the decision to end a human life — cannot ethically be delegated to a system that cannot bear moral responsibility for that decision.

### 7.4 The MAE Protocol in a Military Ethics Context

The author's MAE Gold Code system offers a micro-level illustration of how consent-based behavioral controls can operate in high-stakes, time-pressured environments — a design philosophy with direct analogies to military AI applications. The Gold Code DARK SKY, for instance, provides an instantaneous mechanism for the human operator to constrain system intensity when conditions require reduced engagement. Applied to a military context, this type of hard-coded human override represents exactly the kind of "meaningful human control" that IHL scholars and ethicists argue must be preserved in autonomous systems. The design principle — that system behavior can be instantly constrained by unambiguous human command, with the constraint taking immediate precedence over system goal-seeking — is the consent architecture applied to the highest-stakes domain.

---

## VIII. Governance Frameworks: UNESCO, EU AI Act, NIST AI RMF

### 8.1 UNESCO Recommendation on the Ethics of Artificial Intelligence (2021)

Adopted on November 23, 2021, by all 193 UNESCO member states, the Recommendation on the Ethics of Artificial Intelligence is the first global standard-setting instrument on AI ethics. Its aspiration is comprehensive: it addresses the full lifecycle of AI systems, from data collection and model training through deployment, monitoring, and decommissioning ([UNESCO, 2021](https://unesdoc.unesco.org/ark:/48223/pf0000380455)).

The Recommendation establishes four core values: respect for human dignity and rights; promotion of peaceful, just, and interconnected societies; environmental sustainability; and cultural diversity. These values are operationalized through eleven principles: proportionality and "do no harm"; safety and security; fairness and non-discrimination; sustainability; right to privacy and data protection; human oversight and determination; transparency and explainability; responsibility and accountability; awareness and literacy; multi-stakeholder and adaptive governance; and international collaboration ([UNESCO, 2024](https://www.unesco.org/en/artificial-intelligence/recommendation-ethics)).

The Recommendation's strength lies in its breadth and its explicit requirement that "AI systems must not displace ultimate human responsibility and accountability." Its limitation — common to non-binding instruments — is enforcement: member states are invited, not required, to translate its principles into national legislation. The Recommendation represents normative consensus without binding obligation, which is valuable for establishing shared ethical vocabulary but insufficient for disciplining systems whose operators face market pressure to prioritize capability over compliance.

### 8.2 EU Artificial Intelligence Act (2024)

The EU Artificial Intelligence Act, which entered into force in 2024 with phased implementation through 2027, represents the most ambitious attempt to date to translate AI ethics principles into enforceable law ([European Commission, 2025](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai)). Its core architecture is a risk-tiered classification system: AI systems are categorized as unacceptable risk (prohibited), high risk (heavily regulated), limited risk (transparency obligations), or minimal risk (unregulated).

Prohibited systems include those that deploy subliminal manipulation, exploit vulnerabilities, conduct mass biometric surveillance in public spaces, and enable social scoring by governments. High-risk systems — including those used in critical infrastructure, education, employment, essential services, law enforcement, migration, and justice — are subject to mandatory risk management systems, high-quality data governance, technical documentation, transparency obligations, human oversight, robustness, and accuracy requirements ([WilmerHale, 2024](https://www.wilmerhale.com/en/insights/blogs/wilmerhale-privacy-and-cybersecurity-law/20240717-what-are-highrisk-ai-systems-within-the-meaning-of-the-eus-ai-act-and-what-requirements-apply-to-them)).

The EU AI Act's Article 14 human oversight provision — requiring that high-risk systems be designed for effective human oversight, with individuals able to understand, monitor, and intervene in system operation — represents the most detailed regulatory articulation of meaningful human control currently in force. The Act's enforcement mechanism — a European AI Office with investigative and sanctioning authority — gives it teeth that the UNESCO Recommendation lacks. The rules for high-risk AI systems come fully into effect in August 2026 and August 2027.

| Governance Feature | UNESCO Recommendation | EU AI Act | NIST AI RMF |
|---|---|---|---|
| Binding Authority | No | Yes | Voluntary |
| Geographic Scope | Global (193 states) | EU Member States | U.S. (global influence) |
| Risk Classification | No | Yes (4 tiers) | Contextual |
| Human Oversight Requirement | Principle-level | Article 14 mandate | GOVERN/MANAGE functions |
| Enforcement Mechanism | None | EU AI Office | None (voluntary) |
| Bias/Fairness Provisions | Yes | Yes | Yes (MEASURE function) |
| Consent/User Control | Implicit | Transparency obligations | Implicit |

### 8.3 NIST AI Risk Management Framework (AI RMF) (2023)

The National Institute of Standards and Technology's AI Risk Management Framework provides a process-oriented complement to the UNESCO and EU instruments. Where UNESCO establishes values and the EU AI Act establishes legal obligations, the NIST AI RMF establishes a structured methodology for managing AI risks throughout the system lifecycle ([NIST, 2021](https://www.nist.gov/itl/ai-risk-management-framework)).

The framework is organized around four core functions. **Govern** emphasizes organizational culture, leadership commitment, and governance structures for AI risk management. **Map** addresses contextualizing AI systems within their operational environment, identifying potential impacts across technical, social, and ethical dimensions. **Measure** involves risk assessment using both quantitative and qualitative methods to understand the likelihood and potential consequences of AI-related risks. **Manage** addresses risk response — prioritizing and addressing identified risks through technical controls and procedural safeguards ([NIST AI Resource Center, 2026](https://airc.nist.gov/airmf-resources/airmf/5-sec-core/); [Palo Alto Networks](https://www.paloaltonetworks.com/cyberpedia/nist-ai-risk-management-framework)).

The NIST AI RMF's voluntary nature limits its regulatory force, but its influence as a technical standard is substantial: many organizations in government contracting, healthcare, and financial services treat NIST guidance as de facto requirement. Its strength is its process orientation — it provides actionable guidance for organizations navigating AI risk, rather than only stating what outcomes must be achieved.

---

## IX. Case Studies in AI Ethics Failures

### 9.1 COMPAS: When the Algorithm Is the Sentence

In 2016, ProPublica published an investigation of the COMPAS (Correctional Offender Management Profiling for Alternative Sanctions) recidivism risk tool, which was being used in criminal courts across the United States to inform sentencing, bail, and parole decisions. The investigation found that Black defendants who did not go on to commit further crimes were nearly twice as likely as white defendants to be incorrectly labeled high-risk by the system (45% vs. 23%), while white defendants who did reoffend were labeled low-risk at nearly twice the rate of Black defendants who reoffended (48% vs. 28%) ([ProPublica, 2016](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing)).

The COMPAS case illustrates several of the structural problems identified in this paper simultaneously. The system's opacity made it impossible for defendants to contest the reasoning behind their risk scores — a direct violation of due process and the explainability principle. Its deployment in criminal sentencing gave it enormous power over human freedom while bypassing the procedural protections that govern human judicial decision-making. Its racial disparities were not accidental bugs but structural features of its optimization objective. And the mathematical impossibility of satisfying multiple fairness criteria simultaneously meant that the developers had made an implicit value judgment — one that fell disproportionately on Black defendants — while presenting their tool as an objective instrument of science.

The COMPAS case, more than almost any other, demonstrates Ruha Benjamin's New Jim Code thesis in practice: an algorithmic system that "reflect[s] and reproduce[s] existing inequities" while being "promoted and perceived as more objective and progressive than the discriminatory systems of a previous era" ([Benjamin, 2019](https://aas.princeton.edu/publications/research/race-after-technology-abolitionist-tools-new-jim-code)).

### 9.2 Amazon's Hiring Algorithm: The Self-Perpetuating Past

Between 2014 and 2018, Amazon developed an automated resume screening tool designed to identify top candidates for technical roles. The tool was trained on a decade's worth of resumes that successful Amazon employees had submitted — a dataset that overwhelmingly reflected the male-dominated demographic composition of the technology industry. By 2015, Amazon's engineers recognized that the system had learned to penalize resumes that contained the word "women's" and to downgrade graduates of historically women's colleges ([Reuters, 2018](https://www.reuters.com/article/world/insight-amazon-scraps-secret-ai-recruiting-tool-that-showed-bias-against-women-idUSKCN1MK0AG/); [MIT Technology Review, 2018](https://www.technologyreview.com/2018/10/10/139858/amazon-ditched-ai-recruitment-software-because-it-was-biased-against-women/)).

Amazon eventually abandoned the project, but the case remains paradigmatic. The bias was not deliberately programmed; it was learned from data that faithfully reflected an unequal industry. The algorithm was doing exactly what it was designed to do — identifying candidates who resembled past successful hires — and producing systematically discriminatory results as a consequence. O'Neil's analysis of feedback loops applies directly: an algorithm trained on historically male-dominated hiring data will perpetuate male-dominated hiring, which will produce the next generation of male-dominated training data, in a self-reinforcing cycle that buries the original injustice under the authority of empirical evidence.

The Amazon case also illustrates the consent dimension of the problem: job applicants whose resumes were rejected by the algorithm were unaware that an automated system had processed their applications, had no ability to contest the outcome, and received no explanation. The asymmetry of information between the company and the applicants — the latter bearing all of the consequences of the system's biases while knowing nothing about its operation — is a consent failure with material stakes.

### 9.3 The Dutch Childcare Benefits Scandal: Institutional Bias as Algorithm

Between 2005 and 2019, the Dutch Tax and Customs Administration deployed an algorithmic fraud detection system to screen childcare benefit claims. The system used nationality as a risk factor: applicants with dual nationality received higher risk scores than those with Dutch-only nationality, resulting in tens of thousands of families — disproportionately from ethnic minority backgrounds, particularly those with heritage from the former Dutch colonies in the Caribbean and Suriname — being wrongly accused of fraud and required to repay benefits they had legitimately received ([Wikipedia, Dutch childcare benefits scandal](https://en.wikipedia.org/wiki/Dutch_childcare_benefits_scandal); [Amnesty International, 2021](https://www.amnesty.org/en/latest/news/2021/10/xenophobic-machines-dutch-child-benefit-scandal/)).

An Amnesty International investigation described the system as "xenophobic machines," finding that "from the start, racial and ethnic discrimination was central to the design of the algorithmic system." The algorithm incorporated a self-learning mechanism that adapted over time based on its own outputs — with no meaningful human oversight — creating a discriminatory feedback loop that intensified over years of operation. The scandal ultimately caused the resignation of the Dutch government in January 2021, and at least 35,000 families are now identified as wrongly accused victims, many of whom suffered financial ruin.

The Dutch case demonstrates what Benjamin calls "engineered inequity" — the explicit design of technological systems that amplify social hierarchies — combined with what she calls "default discrimination" — the way discrimination grows from socially and historically ignorant design processes. It also demonstrates the particular danger of self-learning systems deployed without meaningful human oversight: the system's own outputs became the next round of training data, compounding discriminatory patterns over time in ways that no human reviewer caught or corrected.

### 9.4 Facial Recognition and Wrongful Arrests

Facial recognition technologies have documented accuracy disparities that fall most heavily on Black women — with some systems showing error rates up to 35% for darker-skinned women compared to under 1% for lighter-skinned men ([Boston Institute of Analytics, 2025](https://bostoninstituteofanalytics.org/blog/the-moral-compass-of-ai-ethics-in-machine-learning-bias-and-responsible-ai/)). In several documented cases in the United States, these error rates have contributed to wrongful arrests — with individuals detained and subjected to criminal investigation on the basis of false algorithmic identification.

The facial recognition cases intersect uniquely with the military AI discussion in Section VII: the same technologies are deployed in law enforcement contexts that share with military contexts the characteristic that errors have catastrophic, irreversible consequences for the individuals affected. When an algorithm is wrong and the consequence is a wrongful arrest, there is no algorithmic correction — there is a person, wrongly imprisoned, bearing the cost of a system that failed to account for their humanity.

---

## X. Toward a Unified Ethical Framework

### 10.1 The Inadequacy of Principles Alone

The history of AI ethics frameworks reveals a persistent gap between principled aspiration and structural accountability. The principles — transparency, fairness, human oversight, non-maleficence, accountability — are not controversial among serious ethical thinkers. What is lacking is not moral consensus but institutional architecture: the mechanisms by which principles are translated into binding obligations, enforced against resistant actors, and adjusted in response to emerging harms.

A unified ethical framework for human-AI interaction systems cannot rest on principles alone. It must integrate normative commitments with institutional structures, technical standards, and enforcement mechanisms. The following section proposes six pillars of such a framework.

### 10.2 Six Pillars of a Unified Framework

**Pillar 1: Consent as Architecture, Not Afterthought**

Consent must be embedded in the design of AI systems as a core architectural feature, not added as a compliance layer after systems are built. This means investing in consent mechanisms at the earliest design stages: what data is collected, from whom, under what conditions; how behavioral parameters are controlled by users; what mechanisms exist for real-time modification and revocation of consent. The MAE Gold Code system demonstrates that such mechanisms are technically achievable — the engineering challenge is not their implementation but the institutional will to prioritize them.

**Pillar 2: Participatory Governance for Affected Communities**

Systems that affect marginalized communities must be designed with those communities, not merely for them. As Noble, Benjamin, and Crawford demonstrate, the absence of affected community participation in AI design is not an oversight but a structural feature of how these systems are developed — and it produces predictable harms. Participatory AI governance requires formalized mechanisms for community input: public comment processes with real influence, community advisory boards with decision-making authority, and mandatory impact assessments conducted with affected populations before deployment.

**Pillar 3: Prospective Accountability through Layered Responsibility**

The accountability gap cannot be closed by assigning all responsibility to a single actor — no single actor possesses sufficient control over complex AI systems to bear that burden. Instead, accountability must be distributed prospectively across a layered responsibility structure: developers bear responsibility for fundamental design choices and bias audits; deployers bear responsibility for context-appropriate implementation and human oversight; operators bear responsibility for real-time monitoring and intervention; and regulatory bodies bear responsibility for setting and enforcing standards. Each layer must have defined obligations that create accountability before harm occurs rather than only after.

**Pillar 4: Meaningful Human Control as Non-Negotiable**

The principle of meaningful human control must be treated as a non-negotiable constraint in high-stakes domains — not as a default that can be traded away for efficiency gains. In criminal justice, healthcare, employment, and military applications, the decision to apply consequential force or deny fundamental rights must remain the decision of a human being who can be held responsible for it. Systems that formally retain "human in the loop" while practically removing the human's ability to exercise genuine judgment — through interface design, time pressure, or information overload — fail to satisfy this requirement.

**Pillar 5: Technical Transparency and Explainability**

For accountability to be real, AI decision-making must be explainable to the humans responsible for it. This requires both regulatory mandates — the EU AI Act's transparency requirements provide a model — and continued investment in explainable AI research. Opaque systems deployed in high-stakes domains must be presumed unfit for use until their reasoning can be made legible to oversight bodies and affected individuals. The burden of demonstrating explainability should fall on deployers, not on those seeking to contest the system's outputs.

**Pillar 6: Adaptive Governance with Enforcement Authority**

AI systems evolve; governance frameworks must evolve with them. The most effective governance structures will combine clear baseline requirements — particularly for prohibited categories of application and minimum human oversight standards — with adaptive mechanisms that allow regulatory bodies to respond to emerging harms without requiring legislative action for each new case. The EU AI Office provides a nascent model; it requires sustained funding, technical expertise, and genuine enforcement authority to fulfill its mandate.

### 10.3 The Integration of Frameworks

These six pillars are not alternatives to the UNESCO, EU, and NIST frameworks — they are integrative principles that can bring those frameworks into coherent alignment. The UNESCO Recommendation provides the value foundation; the EU AI Act provides enforceable rules for the highest-risk applications; and the NIST AI RMF provides the process methodology for implementing risk management. A unified framework treats these as complementary layers of a coherent governance architecture rather than competing alternatives.

The table below summarizes how the six pillars map onto the three existing frameworks:

| Pillar | UNESCO | EU AI Act | NIST AI RMF |
|---|---|---|---|
| Consent as Architecture | Privacy protection principle | Transparency obligations | GOVERN function |
| Participatory Governance | Multi-stakeholder principle | Fundamental rights impact assessment | MAP function |
| Prospective Accountability | Responsibility principle | Article 25 value chain obligations | MANAGE function |
| Meaningful Human Control | Human oversight principle | Article 14 mandate | MANAGE function |
| Technical Transparency | Explainability principle | Article 13 transparency | MEASURE function |
| Adaptive Governance | Multi-stakeholder governance | EU AI Office | Iterative RMF cycle |

---

## XI. Conclusion

The consent problem in AI is not a technical problem. It is a political one: a problem about who holds power over systems that affect human lives, who bears the consequences when those systems fail, and what obligations attach to those who design, deploy, and profit from them. Technical solutions — explainable AI, bias audits, fairness constraints — are necessary but not sufficient. They become effective only when embedded in governance structures that give affected people genuine standing to contest systems that harm them, and when backed by enforcement mechanisms that make non-compliance costly.

The critical scholars reviewed in this paper — Crawford, O'Neil, Noble, and Benjamin — have done the essential work of naming what is happening and identifying who is harmed. The governance frameworks — UNESCO, the EU AI Act, the NIST AI RMF — represent the most serious institutional attempts to date to translate ethical commitments into enforceable structure. The gaps that remain — particularly around consent, accountability, and meaningful human control in high-stakes domains — are not gaps in our ethical understanding. They are gaps in our political will to constrain systems that generate enormous economic value precisely because they externalize costs onto those with the least power to resist them.

For a student of digital forensics, cyberethics, and AI conflict who is also a combat veteran, these are not abstract considerations. The same questions that arise in algorithmic criminal justice — who decides, who is accountable, who bears the cost of error — are the questions that define the ethics of warfare. The soldier who pulls a trigger is accountable. The developer who trains a targeting algorithm and the general who deploys it bear accountability at their respective levels. The question of how to distribute that accountability in systems of increasing autonomy is the defining governance challenge of this technological moment.

The MAE protocol represents this author's practitioner-level response to the consent problem: a system designed from the ground up around the principle that the user's authority over AI behavior must be real, immediate, and unconditional. Gold Codes are not suggestions offered to a system that may or may not comply — they are hard-coded constraints that the system cannot override. DARK SKY means reduced engagement, regardless of what the system might otherwise compute as optimal. This is the consent architecture applied at the scale of one human being's interaction with one AI system.

Scaling that principle — the unconditional authority of the person most affected — to the governance of AI systems at societal scale is the work that remains. It is difficult work, because the systems with the most power over human lives are controlled by actors with the most to lose from genuine accountability. But the framework is within reach: consent as architecture, participatory governance, layered prospective accountability, meaningful human control, technical transparency, and adaptive enforcement. These are not utopian requirements. They are the minimum conditions under which AI systems can be said to serve the people they affect rather than the interests of those who deploy them.

The technology is not the obstacle. The will is.

---

## References

*All citations are integrated inline throughout the text. The following index maps key sources to their sections for reader convenience.*

Benjamin, R. (2019). *Race after technology: Abolitionist tools for the new Jim Code*. Polity Press. https://aas.princeton.edu/publications/research/race-after-technology-abolitionist-tools-new-jim-code

Crawford, K. (2021). *Atlas of AI: Power, politics, and the planetary costs of artificial intelligence*. Yale University Press. https://katecrawford.net/atlas

European Commission. (2025). *AI Act*. https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai

Floridi, L., Cowls, J., Beltrametti, M., Chatila, R., Chazerand, P., Dignum, V., Luetge, C., Madelin, R., Pagallo, U., Rossi, F., Schafer, B., Valcke, P., & Vayena, E. (2019). An ethical framework for a good AI society: Opportunities, risks, principles, and recommendations. *Harvard Data Science Review*. https://hdsr.mitpress.mit.edu/pub/l0jsh9d1

Lieber Institute, West Point. (2026, March 9). *Legal accountability for AI-driven autonomous weapons*. https://lieber.westpoint.edu/legal-accountability-ai-driven-autonomous-weapons/

Moody's. (2025). *Human in the loop: Why human oversight still matters in AI-driven risk and compliance*. https://www.moodys.com/web/en/us/insights/ai/human-in-the-loop-why-human-oversight-still-matters-in-ai-driven-risk-and-compliance.html

National Institute of Standards and Technology. (2023). *AI risk management framework*. https://www.nist.gov/itl/ai-risk-management-framework

Noble, S. U. (2018). *Algorithms of oppression: How search engines reinforce racism*. New York University Press. https://safiyaunoble.com/wp-content/uploads/2020/09/Algorithms_Oppression_Introduction_Intro.pdf

O'Neil, C. (2016). *Weapons of math destruction: How big data increases inequality and threatens democracy*. Crown Publishing. https://sites.uw.edu/mcba/2024/05/24/the-dark-side-of-big-data-insights-from-weapons-of-math-destruction-by-cathy-oneil/

ProPublica. (2016, May 23). *Machine bias: There's software used across the country to predict future criminals. And it's biased against blacks*. https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing

Reuters. (2018, October 10). *Amazon scraps secret AI recruiting tool that showed bias against women*. https://www.reuters.com/article/world/insight-amazon-scraps-secret-ai-recruiting-tool-that-showed-bias-against-women-idUSKCN1MK0AG/

UNESCO. (2021). *Recommendation on the ethics of artificial intelligence*. https://unesdoc.unesco.org/ark:/48223/pf0000380455

WilmerHale. (2024, July 17). *What are high-risk AI systems within the meaning of the EU's AI Act?* https://www.wilmerhale.com/en/insights/blogs/wilmerhale-privacy-and-cybersecurity-law/20240717-what-are-highrisk-ai-systems-within-the-meaning-of-the-eus-ai-act-and-what-requirements-apply-to-them
