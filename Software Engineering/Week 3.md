Requirements engineering

- Requirements for a system are the descriptions of what the systems should do, the services that it provides and the constraints on its operation.

- Requirements Engineering (RE) is:
	- The process of finding out, analysing, documenting and checking these services and constraints.

- User requirements:
	- Statements plus diagrams of system services and any associated constraints.
- System requirements:
	- Detailed descriptions of system's functions, services and operational constraints.


- Functional requirements:
	- Describe what the system should do
	- Depend on the type of software and expected users
	- Described in an abstract way to be understood by system users
	- System requirements are more detailed (input/output, exceptions)
	- Written in a functional requirements specification document, which needs to be complete and consistent.

- Non-Functional Requirements:
	- Often more critical than functional requirements
	- ![[Pasted image 20241010131719.png]]
	- Must be testable, written quantitively so that they can be objectively tested.
	- Metrics for specifying NFR:
		- ![[Pasted image 20241010131927.png]]

Software Requirements Document:
- Official statement of what software developers should implement.
- Covers both user and system requirements, FR and NFR.
- Thick document that has  diverse set of readers.


Spiral view of requirement engineering:
![[Pasted image 20241010132827.png]]


Feasibility study:

- A short, focused study that assesses if the system is useful to the business.
	- Does the system contribute to the overall objectives of the organisation?
	- Can the system be implemented within the schedule and budget using current technology?
	- Can the system be integrated with other systems that are used?


Requirements Elicitation and Analysis:

- Software engineers work closely with stakeholders

- Discovery:
	- Applying several techniques to interact with stakeholders and find out about domain, user, and system requirements

- Classification and organisation:
	- Grouping related requirements, making coherent clusters and associate them with sub-systems of the architecture.

- Prioritisation and Negotiation:
	- Ordering requirements and resolving conflicts.

- Specification:
	- validating and formally documenting requirements.

![[Pasted image 20241010133847.png]]


Elicitation challenges:
- Stakeholders often don't know what they want/need
- Requirements are often expressed in the stakeholder's own terms, and with implicit knowledge of their work.
- Different stakeholders have different requirements which causes conflict.
- Political factors may influence the requirements of the system
- Importance of each requirements may change
- New stakeholders will come with a new set of requirements


Requirements Discovery:

- Brainstorming: creating new ideas - requires voting methods
- Interviews: closed or open, formal and informal.
- Questionnaires: running short, targeted surveys.
- Examination of documents/artefacts: reading current policies and procedures
- Scenarios: running example interaction sessions
- Use cases: textual or graphical using UML
- Prototyping: best in receiving feedback, can be paper, PowerPoint or functional
- Ethnography: watching daily activities and identifying problems that arise


Scenarios:
- a sequence of events and/or actions that are initiated by an actor.

- Starts with assumptions (pre-conditions) and finishes with a description of the system's state (post-conditions)

- Has workflows (paths) within the scenario with a common goal usually structured as follows:
	- Primary path: most common
	- Alternate path(s): less common way to the goal
	- Exception path(s): aiming for the goal but miss it

- 80/20 rule: you'll spend 80% of your time dealing with what happens 20% of the time (alternate paths)

![[Pasted image 20241010135634.png]]


Use cases:

- A piece of functionality presented within a scenario, and performed by the system that can be described by a short name.
- Each use case is associated with its initiator(s) and use case description
- Should describe the functionality from the initiator's point of view

UML Use Case Diagrams:
- Actors are drawn as stick men (human actors) or stereotyped boxes (external systems)
- ![[Pasted image 20241010143855.png]]
- the `<<include>>` relationship:
	- one use case includes the functionality of another
- the `<<extend>>` relationship:
	- one use case extends the behaviour of another use case

- Group related requirements:
	- Give them numbers so they are traceable (e.g. FR1, FR2, NFR1, etc.)
	- Decompose the system into sub-systems and components of related requirements
	- Define relationships between these components
	- Identify which design patterns to employ

Requirements prioritisation:
- MoSCoW:
	- Must:
		- If not included, delivery is a failure
	- Should
		- Important but not as time critica;
	- Could
		- Related to improving user experience
	- Would (or Won't/Wish to)
		- Least-critical and can be delivered in next release

- Rank requirements on an ordinal scale, using different numerical vlaues based on importance
- Ranking can be used with MoSCoW or any other similar method/variant


^ RP with Agile:
- XP's user stories can be used instead of use cases
	- ![[Pasted image 20241010144613.png]]
- Cards usually contain a checklist of tests to validate the requirement later

- Good user stories are INVEST:
	- Independant
		- can be understood without having to read some other user story
	- Negotiable
		- Invitation to discuss, not a contract
	- Valuable:
		- Giving useful outcomes to the stakeholders
	- Estimatable:
		- So we know they are small
	- Small:
		- Fits in one cycle of development
	- Testable:
		- So it can be declared as "completed".

- You can prioritise user stories using user story maps:
	![[Pasted image 20241010144900.png]]

Requirements validation:
- The process of checking that requirements actually define the system that the customer really wants.

- Types of checks:
	- Validity check:
		- Does the system provide the functions which best support the needs of the stakeholders?
	- Consistency check:
		- Are there any conflicts to resolve?
	- Completeness:
		- Are all functions required by the customers included?
	- Realism:
		- Can the requirements be implemented given time and budget?
	- Verifiability check:
		- Can the requirements be tested?


- Ways to conduct:
	- Requirement reviews:
		- Requirements are analysed systematically by a team of reviewers who check for errors and inconsistencies.
	- Prototyping:
		- An executable model of the system in question is demonstrated to end-users and customers
	- Test-case generation:
		- If a test is difficult or impossible to design, the requirements will be difficult to implement.


Requirements specification:
- the process of writing down the requirements in the requirements document.

- almost always written in natural language supplemented by diagrams and tables

- useful guidelines:
	- invent a standard format
	- use language consistently to distinguish between mandatory and desirable requirements (e.g. must/shall,should)
	- use text highlights (**bold**, *italic*, etc.)
	- avoid jargon, abbreviations and acronyms
	- explain rationale