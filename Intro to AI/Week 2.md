- An agent is anything that can be viewed as:
	- perceiving its environment through sensors and
	- acting upon that environment through actuators

- Percept:
	- agent's perceptual input at any given instant

- Percept sequence:
	- complete history of everything the agent has ever perceived

- An agent's choice of action at any given instant can depend on the entire percept sequence observed to date

- An agent runs in cycles of:
	- 1) Perceive
	- 2) Think
	- 3) Act rationally
	
	- Assumption:
		- Every agent can perceive tis own actions (but not always the effects)

- Sensor:
	- A device which detects the change in the environment and sends the information to other electronic devices.
	- An agent observes its environment through sensors

- Actuators:
	- The component of machines that converts energy into motion.
	- Actuators are only responsible for moving and controlling a system.
	- Can be an electric motor, gears, rails, etc.


Agents and Environments:
- Human agent:
	- Sensors: Eyes, ears, and other organs
	- Actuators: Hands, legs, mouth and other body parts 
- Robotic agent:
	- Sensors: Cameras and infrared range finders
	- Actuators: Various motors
- Software agent:
	- Sensors: Keystrokes, file contents, received network packages as sensors
	- Actuators: Displays on the screen, files, sent network packets


Agent Functions and programs:
- An agent's behaviour is described by the agent function
	- Maps from percept histories to actions:
		- f : P* -> A
- Aim:
	- Find a way to implement the rational agent function concisely 

- Agent = agent program + architecture

- Architecture:
	- some sort of computing device with physical sensors and actuators (PC, robotic car)

Agent program:
- Takes the current percept as input from the sensors
- Return an action to the actuators


Rational Agents:
- Chooses actions that maximize the expected value of the performance measure given the current percept sequence

- Agent precepts -> Action sequences -> Environmental changes
	- If the sequence of the states that changes the environment is desirable, then the agent did it's job
	
- Performance measure:
	- An objective criterion for success of an agent's behaviour


PEAS Analysis:
- (Performance measure, Environment, Actuator, Sensor)

- When building a rational agent, task environment must be considered
- Task environment is made up of PEAS:
	- **P**erformance Measure:
		- The unit to define the success of an agent
	- **E**nvironment:
		- The surrounding of an agent at every instant.
		- Keeps changing with time if the agent is set in motion
	- **A**ctuator:
		- A part of the agent that delivers the output of an action to the environment
	- **S**ensor:
		- The receptive parts of an agent which takes the input for the agent


Environment types:
- An environment is everything in the world that surround the agent but is not apart of the agent itself
	- / A situation in which an agent is present.

- Range of task environment is huge,
	- Can be categorised as:
		- Fully Observable (vs. Partially Observable)
		- Deterministic (vs. Stochastic)
		- Episodic (vs. sequential)
		- Static (vs. Dynamic)
		- Discrete (vs. Continuous)
		- Single agent (vs. multiagent)


Deterministic (vs. stochastic):
- Environment is deterministic if the next state of the environment is completely determined by the current state and the action taken by the agent.
	- e.g. rubik's cube
- Environment is stochastic when the outcome of an action is uncertain and involves probability


Episodic (vs. sequential):
- Environment is episodic when the agent's actions are divided into independent episodes and each action is not dependant on the previous actions
	- e.g. image classification
- Environment is episodic if the choice of current action is dependant on previous actions, the agent needs to plan ahead as current choices will affect future actions


Static (vs. Dynamic):
- Static Environments wont change
- Dynamic Environments do change

- Semidynamic:
	- If the environment itself does not change with the passage of time, but the agent's performance score dows


Discrete (vs. Continuous):
- An environment is discrete when there are a finite number of distinct states, actions, and precepts available
	- e.g. a turn based game like tic-tac-toe
- An environment is continuous when the actions performed cannot be numbered.


Single Agent (vs. Multiagent)
- A single agent is when an agent is operating by itself in an environment 
- Multiagent is when there are many agents working together


Agent Structure:
- All agents have:
	- Input = Current percept
	- Output = Action
	- Program = processes input to produce output


Agent Types:
- Reflex agent (simplest):
	- An agent whose action depends only on the current percept
- Model-Based agent:
	- An agent whose action is derived directly from an internal model of the current world state that is updated over time
- Goal-Based agent:
	- Selects actions that it believes will achieve explicitly represented goals
- Utility-Based agent:
	- An agent that selects actions that it believes will maximise the expected utility of the outcome state
- Learning agent (most advanced):
	- An agent whose behaviour improves over time based on experience



Simple Reflex Agents:

![[Pasted image 20241003160924.png]]

- Selects an action based on the current state only ignoring the percept history

- Simplest agents
- Only succeed in fully observable environment 
- Very limited intelligence
- Do not have knowledge of non-perceptual pats of the current state
- Mostly too big to generate and store
- Not adaptive to changes int he environment


Model-based reflex agents:

![[Pasted image 20241003161243.png]]

- Model - Knowledge about "how the things happen in the world"

- Internal state - It is a representation of unobserved aspects of current state depending on percept history

- Handles partial observability by keeping track of the part of the world it can't see now


Goal-based agents

![[Pasted image 20241003161653.png]]

- Knowing the current state of the environment is not enough. The agent needs some goal information

- Takes decisions based on how far they are from completing their goal
- Intend to reduce the distance from the goal
- Agent chooses between multiple possibilites


Utility-based agents

![[Pasted image 20241003162320.png]]

- Looks at the BEST way to reach a goal
- Look for a quicker, safer, cheaper trip to reach a destination.
- Utility describes how "happy" an agent is.
- Maps a state onto a real number which describes the degree of happiness

Learning agents

![[Pasted image 20241003162522.png]]

- Can learn from it's past experiences or it has learning capabilities
- Starts to learn with basic knowledge, then can act and adapt automatically.


