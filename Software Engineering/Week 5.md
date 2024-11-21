Systems analysis is being conducted when we draft technical solutions to our requirements

The deliverable is not yet implementable, but very close to be.

Overlaps with Domain Analysis, but is more technical and definitely a synthesis activity.

- Domain analysis feeds system analysis with information
- Systems analysis delivers more technical solution to meet the requirements
	- i.e., detailed models of the system, modelling of internal mechanism etc.


The object-oriented system System Analyst (SA) role is to:
- Research problems and determine requirements
- Plan technical solutions for an enhanced or new system
	- Derive an outline object design form requirements
	- The design realises all use cases via actor-object and object-object collaboration
	- Objects of the design have a specific responsibility that can be implemented

- Software-based object-oriented modelling was first introduced to simulate real-world entities

Real world entities:
- Software objects representing the entities (e.g. employees, students, orders)

Attributes of entities:
- Object fields (e.g. employee name)

Behaviours:
- Autonomous behaviours:
	- object's own thread executes object's private methods
- Object interactions:
	- Signals sent between objects

The essence of OO models:
- objects interact by passing messages to eachother



UML sequence Diagrams provide the necessary notation to draw objects and sequences of interactions between them.
- 2D diagram - objects are arranged along the top, and interactions are listed underneath in time order going DOWN the page
- Using analysis they help us tie together the sequences in use case descriptions

![[Pasted image 20241024132546.png]]

Boundary objects:
- facilitate interactions with the outside world (usually a UI and API of some sort)
- Manage the dialogue between an actor and the system
- Do not store any data, but may wrap it appropriately 
- At least one is always present in a sequence diagram

Entity objects:
- Model a store or persistence mechanism that captures information (data) in the system

Control object:
- Realise use cases and organise complex behaviours
- Interact with boundary objects to send/receive input/output and interact with actors

![[Pasted image 20241024133315.png]]

Activation bars indicate that the object is active (i.e. is doing something)
- Can be omitted as they can clutter up the diagram
 ![[Pasted image 20241024133421.png]]
- Nested messages are allowed
 ![[Pasted image 20241024133507.png]]
- Different types of messages can be shown
- Synchronous messages:
	- Caller waits until the receiver finishes and returns
- Asynchronous messages:
	- "fire and forget"

![[Pasted image 20241024133939.png]]
Alternatives:
- Alternative fragments show a choice of behaviour in a workflow. 
- A guard is used to evaluate a choice.
- Only one of the options is executed.
![[Pasted image 20241024134746.png]]

- Optional fragments are only executed when their condition is true
![[Pasted image 20241024134818.png]]

- Loop fragments illustrate repetitive sequences
![[Pasted image 20241024135002.png]]
- Fragments can be combines to communicate the appropriate models

- Reflexive calls allow an object to send messages to itself
![[Pasted image 20241024135106.png]]



Deriving objects from Use Cases

Process:

- For each use case:
  1) Pick a few representative scenarios, i.e. primary, alternative and exception paths
  2) Express each scenario/path as a sequence diagram. identifying participation objects and their interactions
  3) Rework the sequence diagrams as communication diagrams
  4) Combine all communication diagrams to derive an outline/overview class diagram

![[Pasted image 20241024140031.png]]

![[Pasted image 20241024140055.png]]

![[Pasted image 20241024140113.png]]

![[Pasted image 20241024140139.png]]


Sequence Diagrams to Communication Diagrams

- UML communication diagrams are another way of interrelating objects in sequence diagrams
- Numbers interactions in sequence diagrams translates them easier to communication diagrams
- Easier to derive class from communication diagrams

![[Pasted image 20241024140412.png]]

Communication Diagrams to Class Diagrams

- Knowing the objects, one can derive a UML class diagram and add further details such as attributes, associations and multiplicities.
- Note that some of these details may need clarification with the business analyst/stakeholders

![[Pasted image 20241024141023.png]]


Finishing by Aggregating all Models
- The process of taking your design form use case to ultimately class diagrams is iterative
- At the end we try to aggregate all the generated models into one outline class model of the software system

