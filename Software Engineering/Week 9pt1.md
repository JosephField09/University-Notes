<u>Enterprise Architecture</u>
- Concerns:
	- modelling the way the enterprise conducts business
	- modelling information systems to support those operations
- Typical Questions:
	- How does the system overlap/interface with other systems in the organisation?
	- Will the system help the organisation to achieve its goals?
	- Is the cost of the system justified?

<u>System Architecture</u>
- Describes the hardware and software elements and interactions between them

- System architects:
	- Address the big picture
	- Insure that the required qualities of the system are accounted for in the design
	- Ensure the required features are provided at the right cost

<u>Software Architecture</u>
- Describes the overall components of an application and how they relate to each other. 
- Design goals:
	- Sufficiency
	- Understandability
	- Modularity 
	- High cohesion 
	- Low coupling
	- Robustness
	- Flexibility
	- Reusability
	- Efficiency
	- Reliability

- Architecture != framework
	- A framework, or library, is a collection of software artifacts that can be used by different applications
	- E.g. Laravel, Django, React.js, Ruby on Rails


<u>Subsystem Communication Styles</u>
- Each subsystem provides services for other subsystems

- Client-server communication
	- Requires the client to know the interface of the server subsystem
		- Communication is only in one direction
	- The client subsystem requests services from the server subsystem and not vice versa
		- The client plays the role of a consumer; while the server is considered to be the supplier
	- Examples of client-server communication can be found in most network-based applications
		- e.g. email systems and most web applications

- Peer-to-peer
	- Requires each subsystem to know the interface of the other, thus coupling them more tightly
	- Each peer has to run exactly the same program and hence all peers provide identical services
	- Is two way since either peer subsystem may request services from the other

	- e.g. Torrent file sharing systems use a distributed hash table

<u>Service Oriented Architecture (SOA)</u>
- Large distributed systems may adopt Service Orientated Architecture
- The basic unit of communication in SOA is the invocation of remote services
	- A service typically refers to a Web service, which:
		- Communicates via Internet protocols (e.g. HTTP) and
		- Sends and receives structured data, e.g. in XML or JSON format
	- In SOA, Services interact via a common communications protocol
		- Resulting system are loosely coupled with each other

- Common principles:
	- Reusable logic is divided into services
	- Services share a formal contract
		- mainly regarding information exchange
	- Services are loosely coupled
	- Services abstract underlying logic
		- The only part of a service that is visible to the outside world is what is exposed via the service's description
	- Services are composable
		- I.e. a service can be made up of other services

- Why SOA?
	- Business use of SOA is justified by a promise of:
		- Easier reuse of services for multiple purposes
		- Better adaptability to changing business environment and available technologies
		- Ability to integrate new and legacy systems
		- Ability to cheaply setup e-business links across the world
