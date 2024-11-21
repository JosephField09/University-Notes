
- Software development lifecycle (SDLC) is a sequence of phases we can follow in order to create a software application

![[Pasted image 20241003131552.png]]

Domain Analysis
- Study what is already there:
	- Literature review, conversations with experts, etc.

Specification (Requirements Engineering)
- Feasibility study, user requirements elicitation and analysis (input form stakeholders), systems analysis etc.

Design
- Model software structures, software prototypes, interface specifications, component models etc.

Implementation
- Source code, database, interfaces, data models, deployment plan, etc

Validation
- Component testing (unit testing, module testing),
- Integration testing (sub-system and system testing),
- user testing (acceptance testing), etc.

Deployment
- Deployed system, user manuals, training documentation, training staff, fault report



Waterfall process
- Easiest way to organise the development
- Large documents and collections created at most stages
- No turning back in the classical model

![[Pasted image 20241003131806.png]]

Cyclic (Iterative/Incremental)
- Cyclically repeating (a subset of) waterfall activities
- A cycle adds a feature or makes improvements
- Typically 1-4 weeks short
- You can, if needed, deploy stakeholders ideas

![[Pasted image 20241003132215.png]]

Incremental vs Iterative:

- Incremental:
	- Adding new features in each version

- Iterative:
	  - Making improvements with each cycle
	
![[Pasted image 20241003132649.png]]


Unified process:

- Inception phase:
	- Project scope, communication with stakeholders, goals, planning, costs
	- Vision document, use case models etc.

- Elaboration phase:
	- Analysing problem domain, eliminating major risks, refining plan
	- Actors defines, clarifying requirements, etc.

- Construction Phase:
	- Delivering the "beta" version, Meeting all the stakeholders' needs, Testing
	- A working project ready to be deployed, test results, documentation, etc.

- Transition phase:
	- Deployment and maintenance of the system, bug reports, training users
	- Project completed and in use, debriefing.



Agile:

- Agile is an approach to software development
- Another answer to the software crisis in the 70s

Manifesto:
- Values individuals and interactions over processes and tools
- Values working software over comprehensive documentation
- Values customer collaboration over contract negotiation
- Values responding to change over following a plan


Agile process and principles:
- Face-To-Face communication among teams and customers
- Customer representative always available
- Software developed in quick iterations and tested continuously 
- Good quality, well documented code
- No long-term planning, but setting long-term goals and visions
- Simple design to meet personal needs, refractor due to changes

- Scrum adds:
	- Communication via several types of regular meetings
	- Stakeholders have to trust developers
	- Prioritisation of features via backlogs like to do lists

- eXtreme Programming adds:
	- Pair programming
	- Sustainable pace, no overtime
	- Shared system metaphors
	- Shared code ownership - anyone can edit


Scrum:
- Developed in 1990, formalised in 1995 by Sutherland and Schwaber
- A framework within which people can address complex adaptive problems, while productively and creatively delivering products of the highest possible value

- Pillars:
	- Transparency: 
		- Everybody involved in delivering the project should understand what is expected and how the process works
	- Inspection:
		- Review the progress at regular intervals
	- Adaptation:
		- Change a process if it is not working, or is not delivering a sensible result

- Values:
	- Pillars come to life and build trust for everyone only when commitment, courage, focus, openness and respect are embodied and lived by the team

- Roles:
	- The Product Owner is responsible for maximising the value of the product and work of the development team
	- The Development Team is equipped with all necessary skills to successfully deliver the product
	- The Scrum Master supports for the Product Owner, the Development Team

- Events:
	- Sprint:
		- time-box to produce a "done" product increment
	- Sprint planning
	- Daily Scrum
	- Sprint Review
	- Sprint Retrospective

![[Pasted image 20241003144448.png]]



UML Activity Diagrams

- Shows high-level actions chained together to represent a business process occurring in our system

![[Pasted image 20241003144610.png]]

- An action starts when it receives a control token.
- Diamonds are used to depict decision or merge nodes

![[Pasted image 20241003144732.png]]

- Multiple actions that run in parallel are depicted using forks and joins
- A flow is broken up into two or more simultaneous flows
- All incoming actions must finish before the flow must proceed past the join

![[Pasted image 20241003144900.png]]


- When time is a factor in an an activity, time events are used to model a waiting period

![[Pasted image 20241003145146.png]]


- When an activity interacts with an external actor or process, messages are send and received.
- These are called signals

- A receive signal wakes up an action, whereas
- A send signal is a message to the external participant

![[Pasted image 20241003145438.png]]

- When send and receive signals are combines, a synchronous flow is depicted
- If only send signals is depicted, the flow is asynchronous
	- (does not wait for a response to proceed)
- A receive signal can replace a starting node

![[Pasted image 20241003145602.png]]

- Interruptions are receive signals that cause activities to stop following their "expected" flows.
- A lightning bolt symbol is used to depict an interruption

- Interruptible regions show the area in which an interruption is expected to occur

![[Pasted image 20241003145807.png]]


- Objects can be depicted either by using object nodes or pins.
- Input pins represent input objects
	- i.e. an action cannot run without an object parameter
- Output pins specify that an object is an output from an action

![[Pasted image 20241003150014.png]]

- Swimlanes or partitions are used to depict which component or participant is responsible for which actions

![[Pasted image 20241003150242.png]]