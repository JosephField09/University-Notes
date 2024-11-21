[[Software Engineering]]
- lecture every Thursday 
- Tutorials on Friday

- 100% computer based open book exam - 2:30hrs
- ![[Pasted image 20240926131437.png]]

- Software engineering refers to the systematic procedures used for the analysis, design, implementation, testing and maintenance of software.
- Known in 1968 as the title for NATO's conference to discuss software issues
- Coined by NASA's scientist Margaret Hamilton in early 60s
- SE's aim to solve the software crisis:
	- Failures due to increasing demands and low expectations


- Software engineering sets apart a hobbyist programmer from a professional software developer

	- It is the standardised, structured and thorough approach to writing code
	- Treats the whole development process from start to finish in a formalised manner
	- Allows us to deliver programs that meet a high quality (rigour)
		- it is correct, efficient and secure


- Systems thinking is the holistic approach to solving problems
	- It focuses on how a system's components interrelate and change over time within the context of the overall missions that the system needs to accomplish



Systems have the following characteristics:
- Central objective
	- All components work together to achieve a common goal
- Integration
	- Components are put together to complete a system
- Interaction
	- The system works as a result of components interacting with each other
- Interdependence
	- A change to one component will affect other components
 - Organisation
	 - The right components in the right place in the right time


Systems have the following types of components:
- Input, processes and output
- Environment: internal and external
- Boundary
- Interface
- Feedback and control
![[Pasted image 20240926135638.png]]

Hierarchy in systems
- Complex systems are compromised of lots of subsystems
- They are arranged in hierarchies and are integrated to achieve the common goal
- Subsystems have their own boundaries, thus interfaces and environment.


Systems and external environments:
- Users and other systems interact with a system via it's components
- The external (operational) environment affects the functioning of a system
- A system's function may be to change its environment
- External environment can be both physical and organisational

Emergent Properties/ Behaviours
- A system is more complex than just the sum of its parts because of the complex relationships between the components
- Once the system components are integrated, properties emerge

- There are tow types of emergent properties:
	- Functional emerge wen all the parts of a system work together to achieve some objective
	- Non-functional relate to the behaviour of the system in its operational environment

System Modelling
- The world is full of systems and sets, with the majority of people only seeing sets
- To propose or improve an existing system:
	- Use our "computer- based vision" to create a system's model out of a system
	- Model it, no matter how crude the overall insight of it might be

- A system's model must have the right level of detail to define:
	- The components that add up to make the system
	- The types of relationships between those components
	- How the components interrelate into the whole system to perform some function
	- How the whole system interacts with its environment


Models are useful for:
- abstraction: Allows the modeller to focus on the most important features of a real-world situation
- Representation: makes one's ideas into a more concrete artefact
- Communication: Help sharing ideas and thoughts that are difficult to put into words
- Early evaluation: No runtime failures, check if requirements are met


Models over modelled Systems:
- A model is quicker and cheaper to build
- One can choose which details to include in a model
- Some models can be used in simulated environments 
	- Cheaper and safer option
- Models evolve and in some cases they don't even need to make sense.


Models in software engineering:
- Software is an abstract entity and so are it's models
- Models of software focus on certain aspects:
	- Code organisation
	- Runtime entities and their responsibilities
	- Overall data flow
	- Messages among entities
- Unified Modelling Language (UML) provides all the tools necessary to produce models

Component diagrams help us plan out the high-level pieces of a system to establish the architecture and mange complexity and dependencies between components. 
![[Pasted image 20240926145732.png]]

Ports are used to depict points of interaction between a component and the outside world.
![[Pasted image 20240926145950.png]]

You can depict the internal structure of a component and use delegation connectors to show the direction in traffic:
![[Pasted image 20240926150527.png]]

