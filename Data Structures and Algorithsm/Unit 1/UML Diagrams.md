[[Unit 1]]

UML Recap
- It is the standard notation for software design
- It is programming language independent
- Typical diagrams include: class diagrams, use case diagrams, sequence diagrams, etc.


UML Class Diagram
- Describes:
	- Classes used in the system
	- Static relationships among the classes
	- Attributes and operations of each class
	- The constraints on the connections among objects


- Four kinds of visibility:
	- + public
	- - private 
	- `#` protected
	- - package
	
![[Pasted image 20240923152842.png]]


- Relationships:
	- Generalization:
		- Relationship between a superclass and its subclass(es)
		- A.K.A an "is a" - a car **is a** vehicle
		- ![[Pasted image 20240923153314.png]]


	- Association:
		- A general description of relationship between two or more classes
		- ![[Pasted image 20240923153438.png]]

	
	- Aggregation:
		- A type of association that is typically known as a "has a" relation
		- e.g. a book **has a** chapter
		- ![[Pasted image 20240923153600.png]]
 
	
	- Composition:
		- A.k.a "composite aggregation" 
		- Typically known as a "owns a"
		- The instance classes are dependent on each other for their existance
		- e.g. a picture of a tree can be composed by a brown rectangle and a green circle
			- both shapes need to exist for the tree to be complete
			- ![[Pasted image 20240923154226.png]]



	- Realisation:
		- Class implements an interface
		- ![[Pasted image 20240923155024.png]]


	- Dependency:
		- uses relations
		- ![[Pasted image 20240923155102.png]]