Heuristic function:
- Estimate of optimal remaining cost from n goal
- Defined using only the state of node n
- E.g. straight line from birmingham to doncaster

- Provides problem specific knowledge to the search algorithm

- g(n): known path cost so far to node n
- h(n): estimate of optimal cost to goal from node n
- f(n) = g(n) + h(n): estimate of total cost to goal through n

 - Greedy Best-First:
	 - order by h(n)
- A* search:
	- order by f(n) = g(n) + h(n)