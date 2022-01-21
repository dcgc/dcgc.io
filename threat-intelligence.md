---
layout: page
title: Threat Intelligence
categories: notes
permalink: /threat-intelligence/
---

CTI Analyst:
- Analyze successful/unsuccessful intrusions by targeted threat actors
- Construct descriptions of campaigns, actors, and organizations
- Seek, collect and exploit intelligence from others
- Generate intel from their own data sources and share it accordingly
- Manage intel to firther the objectives of their organizations

APT is a style, not a definitive category, and needs to be taken into consideration.
- APT is any persistent focused adversary with sufficient resources, not necessarily advanced methods.
- Malware and other ill-intended methods are just a tool; the threat is the human behind the attack.
- Results impact can be costly due to the scope target operated by the APT.
- Increases in threat intelligence on top of already well-functioning security programs can reduce the effectiveness of the threat.
- We should not think of Threat Intelligence as the silver bullet (evidence and data to stop the attacks) but as complementary security procedure, part of security operations center.


**Intelligence collects and processes information about competitive entity and agents (maligned actors), needed by an organization for its security (defense) and well-being (operational).**

Intelligence Sources:
	- HUMINT: Interpersonal (human)
	- GEOINT: Geospatial (satellite)
	- MASINT: Measurement/Signature (radar).
	- OSINT: Open-source collection (Internet, public records).
	- SIGINT: Signal Intercepts (cellphone, taps).
	- ALL SOURCE: Every available source (all above).
- Threat Intelligence falls in ALL SOURCE as we identify several sources and fuse it together.


**Counterintelligence is:**
-	Identification/Assessment/Neutralization/Exploitation of intelligence activities of adversarial entities.
-	CTI is Counterintelligence

**Definitions:**
-	Analysis is to deconstruct intrusions and threat actors.
-	Synthesis is to construct objects based on unsuccessful intrusions (enhancing understanding of the intrusion), adversary profile and campaigns.
-	Analytical Judgement uses a process to search for, sort, structure and evaluate data and information. There is never enough time or data; decisions still need to be made.
-	Good CTI thinks about how they think and reaching a conclusion is defensible, repeatable and understandable to others. CTI’s have different views (people are different). Perception should be active.
-	Bias is a hindrance to analysis and impossible to eliminate, difficult to understand. Guarantee diversity of CTI analysts (knowledge type) and collaboration between each other to favor less bias. Different backgrounds can also help (e.g., APT is Russian and CTI Analyst understands Russian).
-	Adversary intent is one of the most difficult goals in intelligence analysis.
-	Data: sets of values and individual elements of what makes up information. 
-	Information: collection of data that can answer yes or no questions.
- Intelligence: analyzed information. _We cannot collect all the data._
- Intent: what the actor seeks to achieve
- Opportunity: conditions necessary to achieve threat objectives.
- Capability: degree to which adversary can succeed in accomplishing objectives.
- Threats can be established by evaluating Capability + Intent + Opportunity.
- Impact: effect of compromise on organization.
- Vulnerability: susceptibility of organization to compromise of CIA.
- Risk: likelihood of exploitability of a vulnerability, a successful high impact and/or leverage of the threat.


**Types of Analysis:**
- Data-driven: accuracy based on dataset’s accuracy and completeness.
	-	Should be Logically driven.
	-	Use Good datasets.
-	Conceptually-driven: accuracy based by feedback over time.
	-	Immediate interpretation of complex concepts.
	-	Numerous unknowns and undefined variables and relationships.
-	Structured Techniques: approaches in better evaluating information while reducing impact of bias.
	-	Data into buckets allows for the abstraction of the CTI analyst and identification of patterns.
	-	E.g., Analysis of competing hypotheses, devil’s advocate, Team A/B, High-Impact/Low-Probability, Brainstorming, Red Team
-	Mental Models: experience based on assumptions and expectations.
	-	Combination of cognitive and perceptual biases that can hinder analysis.
-	Mosaic Theory: inappropriate belief that there is only one mosaic to make.
	-	Disparate information comes together to tell the right story.
	-	Rarely practical and heavily based on analyst interpretation.
-	Other: descriptive (describes elements of data), explanatory (structure “why” of the situation), evaluative (understand what information means), estimative (“what will happen next?”).

**Intelligence Life Cycle**
- P&D: gaps identified and prioritized; plan is set forth to where and how analysts will get the data and information they need.
- Collection: plan execution and data collected to fit gap.
- P&E: preparation for raw data collection.
- A&P: while analyzing, more information is needed (more collection needs to occur).
- Dissemination: distribution of requested intelligence to interested party (with information disseminated, there might be questions (cycles repeat)).
- RFI: Request for Information; questions to SME, clarifications to CTI, etc.

**CTI Analysis Elements:**
-	Primitives (terminology)
-	Axioms (accepted assumptions)
-	Abstractions (models)
	-	Visual representations
	-	Generalizations
	-	Transformations

**Intrusion Analysis: fundamental CTI skill:**
-	Intrusions are attempts, successful or failed, that adversary makes to compromise or attack systems.
-	Failed intrusions often represent first methods to compromise an organization in which might have commonality with first methods used against other organizations or even overlaps with future tradecraft leveraged.

**CTI Terminology**
-	Intrusion
-	Adversary/Threat: individual(s) involved in execution of an intrusion.
-	Compromise/Breach: successful violation of data confidentiality or integrity what was the intent of the adversary.
-	Pivot: leveraging intelligence to identify additional intelligence.
-	Campaign: adversary mission focus.
-	TLP (Traffic Light Protocol): see image below
-	Victim: individual/system compromised while achieving objective.
-	Target: intended victim of an intrusion.
-	Attack: intrusion executed with the intent of catastrophic outcomes (sabotage).
-	Persona: fake name or identifier that adversary takes.
-	TTP’s (Tactics, Techniques and Procedures): tactic is higher-level tradecraft that the adversary intends to use to reach an objective; technique is manner to which the adversary is going to accomplish that tactic; procedure is more granular approach to accomplishing the technique.

**Indicators of Compromise**
-	Instrumentation
-	Adequate actions
-	Complete analysis

Indicator of Lifecycle describes how indicators beget indicators. It is a cycle enabled by people, processes, and technology of discovery, maturation and exploitation. It can be represented as a directed-graph state diagram describing the states and transitions that move an indicator between states. It suggests that on must have intelligence in the first place in order to acquire more intelligence. A large amount of intelligence about one adversary may not help at all against another adversary for whom an organization has no intelligence whatsoever. This is a shortcoming of the CTI approach that must be addressed in ways other than analysis and network defense; intelligence sharing helps fill this void.

**Revealed:** intelligence has been revealed t us about a specific threat to the assets we intend to defend.

**RTU (Reported to Us):** threat intelligence feeds from other organizations (given to us); these indicators will typically have less context, may be difficult to operationalize, and will have less context around them than internally derived indicators.

**Vet & Operationalize:** Vetting process includes determining the viability of using the information in hand either alone or to detect the malicious activity in the specific environment one is defending. Involves assessing whether the intelligence is reliable and whether it is good intelligence and adequately represents the malicious activity from which it was derived in a way that is actionable in a particular environment. 

**Mature:** leverage the indicator for the discovery course of action; this action is research oriented. What must first be done is historically searching available data sources to discover whether this was observed in the past, and if so, investigate further to determine whether the activity was malicious or benign. Or two CoA’s should be applied: detect and the best available mitigating action, if any exists.

**Utilized:** indicators that are viable in one environment may not be viable in another; once vetted indicator is assigned to a course of action and deployed, and that course of action matches the network/system activity. Usually manifests in a log in log searching (discovery) or IDS rule firing (detection).

**Intrusion analysis:** indicator will rarely have or represent a complete set of malicious activity on its own, meaning that a CTI analyst must build a complete picture of the intrusion. The process of articulating each phase of the Kill Chain beginning with the utilized indicator will reveal many more indicators, each of which will then begin the life cycle anew. All intrusions potentially have additional indicators to be revealed once identified.

_A CTI Analyst should be responsible in building detections off indicators revealed in an IR effort. The Indicator Lifecycle is not about how useful an indicator, but how it is based on its maturity and confidence we have in it. Only indicators that are characterized by this should be subject to a high level of analytical rigor and instrumentation._

**Key indicators:**
-	Identify as many intrusions as possible.
-	Remain consistent across multiple intrusions.
-	Ideally at least two in different Kill-Chain phases to define campaign.
-	Uniquely distinguish a campaign from other campaigns.
-	Distinguish campaign from benign activity.
-	Ideally across three or more intrusions.
-	Align to a phase of adversary activity.

Discovery and Indicator Life Span:
-	All intelligence has useful lifespan.
-	Adversaries alone dictate lifespan.
-	Intelligence is useful until it is not.
-	Retire indicators when FP arise.
-	Computational limits no excuse.

_Keep all your detections and all your indicators until their presence causes a problem. When computational becomes a problem, redesign, replace, or re-engineer how your detections and frameworks they ride on operate. I have accepted with naivety some of them but knowledgably rejected some._

Indicator Fatigue and Proper Use Cases:
-	Indicator Sweeps:
	-	Develop indicators specific to the intrusion
	-	Use indicators to scope incident or sweep to ensure it was cleaned up correctly
-	Addressing Knowledge gaps
	-	Observe methods used by threats in other intrusions to get missing information
	-	Addresses missed phases in kill chain
-	Enrichment
	- Leveraged against larger datasets for enrichment
	- Often research value more than concrete detections such as unique correlations in SIEM

Organizations and teams can either focus on actuating on intelligence or on producing intelligence. A team can bounce back and forth between these two concepts (but not doing both at the same time).

