Business analysis

Analysis:
- An investigation of the component parts of a whole
- Involves some kind of abstraction

Synthesis:
- Creating something real out of abstract models

![[Pasted image 20241017130752.png]]

Business Analysis

- Business Analysis is the set of tasks and techniques we use when working with stakeholders to understand the structure, policies and operations of an organisation

A business analyst:
- Identifies business problems and opportunities
- Elicits the needs and constraints from stakeholders
- Analyses the needs and defines requirements
- Assesses and validates the potential and actual solutions


Man focus on business goals and not technology designs
- BAs to Developers ratio 1:6 but now changing towards BAs

When describing a business, there are four basic requirements components:
1) Information is data
2) Manual or automated activities and procedures the business performs
3) People (or systems or departments) inside and outside the organisation
4) Guidelines, constraints and policies under which the organisation operates

![[Pasted image 20241017132429.png]]

- business analyst breaks requirements down and determines where improvements need to be made


Conducting business analysis:

- Business process maps:
	- ![[Pasted image 20241017132544.png]]
	- A business process is a logical grouping of events that can be agreed as a fundamental element of the business

	- A business process map is a collection of named processes grouped hierarchically on no more than 3 levels
	- Rules of thumb:
		- Root is the most abstract process
		- Level 1 should not have more than 10 high-level processes

	- ![[Pasted image 20241017132758.png]]
	- A lower-level process is a specialisation of its parent

	- ![[Pasted image 20241017132832.png]]
	- breaking down to more than 3 levels will make the business process map useless 

	- Business process maps help us focus on the main functionality

	- What to avoid:
		- No need to present a perfect breakdown
		- Does not show:
			- The structure of the organisation
			- Information flow
			- Time considerations
			- Interactions among processes

	- Method to produce a business process map:
		- usually a half-a-day workshop attended by business managers and experts
			- all contribute to knowledge but need to reach an agreement

		- Need for a facilitator:
			- Oversees the discussions and forces rules
			- Aiming for a high-level view, and a good but not perfect map
			- Ensures timing


- Identifying Domain Objects
	- Noun-verb analysis: the first step to class decomposition.
		- To break a large problem down into a class structure

	- Nouns may represent:
		- Classes
		- Specialisations (classes that extend abstract classes)
		- Attributes (i.e. a Student has a name)
		- Data (values to attribute variables/containers/etc.)

	- Verbs may represent:
		- Services (i.e. methods) provided by a Class
		- Services used by Classes


- UML Object and Class Diagrams
	- UML object diagrams are used to communicate object information 
	- Represent instances of classes and derive from UML Class Diagrams
	- Object diagrams may or may not contain object attribute values

	- Notation: 
		- myCup : Cup (myCup is an instance of class Cup)

	- ![[Pasted image 20241017143152.png]]

	- ![[Pasted image 20241017143207.png]]

	- ![[Pasted image 20241017144530.png]]

- A detailed class diagram
	- Class diagrams can be very detailed
	- - private, + public, #protected, / derived
	- Parameters and return types
	- Interface and abstract  
		- (realisation and specialisation arrows)

- State machine diagrams
	- Used to show how an object's state changes during its lifetime
	- Object state = attribute values
	- Drawing state machine requires increase of abstraction

	- ![[Pasted image 20241017144920.png]]
	- Object states can be a passive quality (on or off) or an active quality (i.e. the object is doing something)
	- ![[Pasted image 20241017145217.png]]
	- Objects transition from source states to target states
		- ![[Pasted image 20241017145228.png]]

	- Composite states 
		- UML allows concurrent states to be shown using the composite states notation
		- e.g. an NPC in neutral state with substances of searching and pacing
		- ![[Pasted image 20241017145347.png]]
		- Composite state is complete when every substate diagram is complete

	- History states are used to remember the states before an interruption happened
		- ![[Pasted image 20241017145522.png]]
	- Advanced pseudo states
		- UML notations allows choice, forks and joints to be possible
		- ![[Pasted image 20241017145609.png]]


Use a UML state machine to:
- Show event driven objects in a reactive system
- Describe how an object moves through various states within its lifetime
