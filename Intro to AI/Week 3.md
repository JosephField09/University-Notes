- solving problem by searching:
	- goal based agents (problem solving)
	- reflex agents


![[Pasted image 20241010152307.png]]


![[Pasted image 20241010152334.png]]


![[Pasted image 20241010152415.png]]

![[Pasted image 20241010152603.png]]


Search: Evaluate a search algorithm

- Strategies are evaluated based on:
	- Completeness
		- Does it always find a solution if one exists?
	- Time complexity:
		- Number of nodes generated/expanded
	- Space complexity:
		- Maximum number of nodes in memory
	- Optimality:
		- Does it always find a least-cost solution

	Time and space complexity is measures in terms of:
	- **b** - maximum branching factor of the tree
	- **d** - depth of the least-cost solution
	- **m** - maximum depth of the state space

Difficulty:

- At the start of the search, the algorithm doesn't know:
	- size of the tree
	- shape of the tree
	- depth of the goal states

- How big can a tree be?
	- constant branching factor of b
	- goal exists at depth d
	- search tree that incldues a goal can have $b^d$ different branches in the tree (worst case)

Search algorithms:
- Uninformed (or blind)
	- Have no information about the number of steps or the path cost from the current state to the goal

	- Breadth-first search (BFS)
		- ![[Pasted image 20241010154649.png]]
	- Depth-first search (DFS)
		- ![[Pasted image 20241010154715.png]]
	- Depth limited search
	- Iterative Deepening Search

- Informed(or heuristic)
	- uses considerations to prefer choices

	- Greedy search
	- A* search


![[Pasted image 20241010154736.png]]

![[Pasted image 20241010154747.png]]