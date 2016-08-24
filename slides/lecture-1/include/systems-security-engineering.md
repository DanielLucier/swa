class: center, middle
template: inverse
# Systems Security Engineering
???
This slide deck is largely based on the content from Chapter 2 of NIST 800-160 Public draft 2 Systems Security Engineering Public Draft 2. http://csrc.nist.gov/publications/drafts/800-160/sp800_160_second-draft.pdf 

Another update to this document is going to be released soon in Fall 2016. Keep an eye out for it.

---

class: center, middle
![Dilbert](http://assets.amuniversal.com/b7797c402f4901348be4005056a9545d)
???
Systems security engineering is hard. Particularly, when you have a well-resourced and capable adversary.

---

# Agenda
1. Need for Security Engineering
1. Terminology
1. Security Engineering Perspective
1. Security Engineering Framework

---

# Need for Security Engineering
## Tiers of vulnerabilities within organizations
- Known vulnerabilities
- .red[Unknown] vulnerabilities
- .red[Adversary-created] vulnerabilities

--

## Visible Vulnerabilities
- Discovery and patching

--

## Invisible Vulnerabilities
- Sound security engineering

???

2013 Defense Science Board Task Force described several tiers of vulnerabilities within organizations including known vulnerabilities, unknown vulnerabilities, and adversary-created vulnerabilities. The important and sobering message conveyed by the Defense Science Board is that the top two tiers of vulnerabilities (i.e., the unknown vulnerabilities and adversary-created vulnerabilities) are, for the most part, totally invisible to most organizations. These vulnerabilities can be effectively addressed by sound systems security engineering techniques, methodologies, processes, and practices—in essence, providing the necessary trustworthiness to withstand and survive well-resourced, sophisticated cyber-attacks on the systems supporting critical missions and business operations.

---
class: center, middle
# Icebergs*
![iceberg](http://www.newfoundlandlabrador.com/Content/images/iceberg-safety-iceberg-facts.png)

.footnote[
\*.red[above the waterline] and .red[below the waterline] problems
]

???

If we think of an iceberg, the visible vulnerabilities are above the waterline and the invisible ones are the ones below. It is the invisible ones that are difficult to address and can potentially sink the ship!

We will refer to "above the waterline" and "below the waterline" problems

---
class: center, middle
# Starting with the Right Abstractions
.top-right[
    ![Abstractions](http://www.espen.com/graphics/math-answer-findx.gif)
]

---

# Terminology

## System
Combination of interacting .red[elements] organized to achieve stated purposes

--

## System Element
Recursively defined as a .red[system]  
Member of a set of elements that constitute a system  

_Examples: hardware; .red[software]; firmware; data; facilities; materials; humans; processes; and procedures_

???
# System and System Element
* The recursive definition of a system element allows us to support the notion of a system of systems.  
* The term **system** may apply to a collection of elements or a single element
* One observer's system may be another observer’s system element.  

---

# Terminology

## System-of-Interest
System that is the focus of the .red[engineering] effort

## Enabling System
System that supports a .red[system‐of‐interest] during its life cycle stages but does not necessarily contribute directly to its function during operation  

_Examples: computer‐aided design tool, prototype, test harness, trainer, code compilers, and code assemblers_

???
# System of Interest
* The term system-of-interest is used to define the set of system elements, system element interconnections, and the environment that it operates in.

---

# Terminology

## Other Systems
System that interacts with the .red[system‐of‐interest] in its operational environment

_Examples: a global positioning system space vehicle being an “other system” interacting with a GPS receiver as the “system‐of‐interest.”_

---

class: center, middle
![NIST SP 800-160 Public Draft 2](images/view.png)  
Systems Engineering View

???
# Things to note:
* The system of interest identification scopes the set of system elements, system element interconnections, and the environment that it operates in
* All _other systems_ that interact with the system of interest are included in the operational environment
* Some enabling systems may exist outside the environment of operation, for example, the compiler used at the developer site, open source developer


# Can you think of _other systems_ that introduce risk?
# Can you think of _enabling systems_ that are introduce risk?

---

# Security Engineering Perspective

## .red[Security]
Freedom from conditions that can cause _loss of assets_ with _unacceptable consequences_
--

## .red[Engineering challenge]
Engineer _protection capabilities_ for:
1. .red[assets] to which security applies and 
1. .red[consequences] against which security is assessed

???

# Conditions
These can be adversity in the form of disruptions, hazards, and threats and are considered synonyms for “bad things that happen” that are of interest to systems security engineering

# Consequence
[ISO/IEC 15026-1]
Effect (change or non-change), usually associated with an event or condition or with the system and usually allowed, facilitated, caused, prevented, changed, or contributed to by the event, condition, or system.


---

# Security Engineering Perspective

## Goal: _have .red[protections] capabilities built-in..._

--

### .red[Active Protections] 
* .red[Mechanisms] that exhibit security behavior with functional and performance properties to satisfy security requirements

--

### .red[Passive Protections]
* Provides the environment for the .red[execution] and .red[construction] of all mechanisms (general purpose and security)

???

# Active Protection: 
These mechanisms explicitly satisfy security requirements that address the behavior, interaction and utilization of and among technology/machine, environment, human, and physical system elements.

# Passive Protections:
For example, developer training in secure coding provides for the construction of security mechanisms with a higher level of assurance. Simillarly, a fully patched and hardened java runtime environment provides a protection capability to the hosted java applications. A visual studio complier with the appropriate compiler flags is also a passive potection. 


---

# Protection Examples

## Active Protections

- Access control
- Single signon
- Identification
- Authentication
- Encryption at rest and in transit
- Configuration files
- Backup
- Two-phase commit
- ...

---

# Protection Examples

## Passive Protections

- Architecture (partitioning into domains)
- Design (a process for defining system elements, interfaces and other characteristics)
- Coding guidelines
- Code review
- Developer and user training
- Verified and configured compilers
- Acquisition policies
- Red-teaming
- Project management
- ...

---

# Adequate Security

## A well-reasoned sum of both active and passive protections 
--

### For all .red[system execution modes]
e.g., initialization, operation, maintenance, training, shutdown
--

### For all .red[system states]   
e.g., secure, nonsecure, normal, degraded, recovery
--

### For all .red[transitions] 
Between system states and between system execution modes.

---
# Security Engineering Framework

### .red[Problem] Context
A sufficiently complete understanding of the problem
--

### .red[Solution] Context
Transforms the security requirements into design requirements for the system
--

### .red[Trustworthiness] Context
Assurance Case: An evidence-based demonstration, through reasoning, that the system-of-interest is deemed trustworthy

???
The framework is independent of system type and engineering or acquisition process model and is not to be interpreted as a sequence of flows or process steps but rather as a set of interacting contexts, each with its own checks and balances

---

# Problem Context
### .red[Security objectives]: What it means to be _adequately_ secure for the assets and the consequences of asset loss againsts which security will be assessed
--

### .red[Measures of success]: Strength of protection and level of assurance in the engineered protection capability
--

### .red[Life cycle security concepts]: Distinct contexts for interpretation of security and the associated processes, methods, and procedures
--

### .red[Security requirements]: Specifies the functional, assurance, and strength characteristics for a protection mechanism

???

# Security Objectives and Measures of Success
The security objectives have associated measures of success. The two combine to drive the development of security requirements and the development of assurance claims

# .red[Life cycle security concepts]: 
- Concept 
- Development 
- Production 
- Utilization 
- Support
- Retirement


---

# Solution Context

### .red[Define security aspects of the solution]: 
- The security architecture views and viewpoints
- The security design
- Security performance verification measures

### .red[Realize security aspects of the solution]: 
- Implementation of the system security design

### .red[Evidence for security aspects of the solution]: 
- Analysis, demonstration, inspection, and test

---

# Trustworthiness Context

### .red[Developing and maintaining the assurance case]
- Assurance cases are developed for claims based on the security objectives and associated measures of success

### .red[Demonstrating that the assurance case is satisfied]
- An assurance case is a well- defined and structured set of arguments and a body of evidence showing that a system satisfies specific claims with respect to a given quality attribute	

???
Assurance cases also provide reasoned, auditable artifacts that support the contention that a claim or set of claims is satisfied, including systematic argumentation and its underlying evidence and explicit assumptions that support the claims [ISO/IEC 15026-2]

---
class: center, middle
![NIST SP 800-160 Public Draft 2](images/framework.png)  
???
# Systems Security Engineering Framework
Establishing problem, solution, and trustworthiness contexts as key components of a systems security engineering framework ensures that the security of a system is based on achieving a sufficiently complete understanding of the problem as defined by a set of stakeholder security objectives, security concerns, protection needs, and security requirements. This understanding is essential in order to develop effective security solutions &mdash; that is, a system that is sufficiently trustworthy and adequately secure to protect stakeholder’s assets in terms of loss and the associated consequences.

# System security analyses 

Employ concepts, principles, means, methods, processes, practices, tools, and techniques from the security perspective to provide relevant data and technical interpretations of issues from the security perspective

Support gradation:  
\* Differentiated to align with the scope and objectives of where they are applied within the systems security engineering framework 

\* Performed with a level of fidelity, rigor, and formality to produce data with a level of confidence that matches the assurance required by the stakeholders and engineering team

---

class: center, middle
![NIST SP 800-160 Public Draft 2](images/framework-course-topics.png)  

---

class:center, middle
# Next Up
Constructing Assurance Cases using Goal Structuring Notation

---

![lifecycle processes](images/systems-engineering-lifecycle-processes.png)
