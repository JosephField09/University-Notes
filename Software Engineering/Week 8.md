- Analysis identifies "what" the system must do
- Design specifies "how" it will do it

- In analysis, the analyst seeks to understand the organisation, its requirements, and its objectives
- In design, the designer seeks to specify a system that will:
	- Fit the organisation
	- Meet its requirements adequately, and
	- Assist it to meet its objectives


Logical design:
- Independent of the implementation language and platform
- e.g. for UI, types of fields, position in windows, etc

Physical design:
- Constrained by the implementation platform and language
- e.g. layout managers available, etc.

System design:
- Deals with the high level architecture of the system
- E.g. structure of sub-systems, communication between them, and their distribution on processors.

Detailed design:
- Deals with e.g. inputs, outputs, processes and file/database structures


Good design qualities:
- Functional: The system will perform its required functions
- Efficient: The system performs those functions efficiently in terms of time and resources
- Economical: Running costs of system will not be unnecessarily high
- Reliable: Not prone to hardware or software failure, will deliver the functionality when the users want it
- Secure: Protected against errors, attacks and loss of valuable data

- Buildable: The design is not too complex for the developers to be able to implement it
- Maintainable: The designer's intention is clear to a maintenance programmer
- Usable: Provides users with a satisfying experience
- Reusable: Elements of the system can be reused in other systems
- Flexible: Capable of being adapted to new uses, to run in different countries or to be moved ot a different platform



Design addresses the issue of how to meet the requirements
- Non-function requirements, in particular, impact on the design
- Measurable objectives should be formulated for these requirements so that they can be tested


Trustworthiness seeks to address the quality and robustness of software, ensuring that the software "performs as it should when it should and how it should" (UK-TSI, 2016)
- We use software in our daily life, so it is important 

Trustworthy Software Foundation (TSF) summarises 5 facets of trustworthiness:
- Safety:
	- Software should operate without causing harm to anything or anyone
- Reliability:
	- Software should operate correctly
- Availability:
	- Software should operate when required
- Resilience:
	- Software should recover from errors quickly and completely 
- Security:
	- Software should remain protected against the hazards posed by malware, hackers or accidental misuse



Architecture
- Defines structure and behaviour
	- What are the core components, and how do they interact with each other
- Balances stakeholders' needs which may conflict
- Has a particular scope
	- e.g. enterprise, system, software
	- More on this distinction next week
	- For today we will look ahead to subsystems

Subsystem
- Typically groups together system elements with some common properties
- Advantages:
	- Produces smaller units of development in a system which may be complex
	- Helps to maximize reuse, maintainability and portability at the component level

- Two general approaches to divide a system into subsystems:
	- Layering: Different subsystems usually represent different levels of abstraction
	- Partitioning: Usually means that each subsystem focuses on a different aspect of functionality
	- Both approaches usually used together on one system


![[Pasted image 20241114141612.png]]

Layers architecture:
- Logical structuring
- Group functionality / code based on its level of abstraction
- All layers may reside on the same computer

Tiered architecture:
- Concerns the logical grouping of functionality / code, BUT
- Tiers reside on, and are executed by, different computers

![[Pasted image 20241114142100.png]]


<u>Model-View-Controller (MVC)</u>

![[Pasted image 20241114142201.png]]

- Model:
	- Represents data and the rules that govern access to and updates of this data

- View:
	- Renders the contents of a model and must update its presentation as .
	- May register itself with the model for change notifications, or may call the model to retrieve the most current data

- Controller:
	- Translates the user's interactions with the view into actions that the model will perform.

![[Pasted image 20241114143338.png]]

- CalcMVC:
	- Top level class
	- Responsible for creating the model, view and controller objects

- CalcModel:
	- Does not know about the view nor the controller
	- Fires property change notifications to its subscribers, in this case, the view

- CalcView:
	- Renders data from the model using a GUI
	- Subscribes to the property change notifications from the model
	- Passes user input events to its subscribers

- CalcController:
	- subscribes to all user input events
	- defines the event handlers for GUI events
	- calls the model to change its state based on user event

![[Pasted image 20241114145252.png]]

- MVC architecture is flexible 
- Multiple views can be created in the MVC architecture
- Changes made to the model within one view is reflected immediately to all views which use the same model.