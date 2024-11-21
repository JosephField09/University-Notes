<u>Stack Basics</u>
- A stack is a Last-In-First-Out (LIFO) data structure.
- Operations:
	- `push`: Add an element to the top
	- `pop`: Remove and return the top element
	- `peek`: View the top element without removing it
	- `isEmpty`: Check if the stack is empty

<u>Application of Stacks</u>

- Undo Functionality:
	- Tracks operations in reverse order for rollback
	- E.g. Spreadsheets use stacks to manage undo operations

- Runtime Environment:
	- Tracks method calls using activation records on a runtime stack.
	- Helps return control after method completion.

- Maze Traversal
	- Represent maze as a 2D array (1:path, 0:wall)
	- Use stack to record potential moves
	- Mark visited cells and backtrack using the stack until the target is reached or paths are exhausted
	- ```
		stack.push(new Position(x, y)); // Push valid moves 
		pos = stack.pop(); // Move to a new position 
		if (grid[x][y] == finish) done = true; // End condition

- Postfix Expression evaluation
	- Use a stack to process expressions where operators follow operands.
	- Algorithm:
		1. Scan left-to-right
		2. Push operands to the stack
		3. On encountering an operator, pop two operands, evaluate, and push the result
		4. Final result is at the top of the stack
	- ```
		while (tokenizer.hasMoreTokens()) { 
			token = tokenizer.nextToken(); 
			if (isOperator(token)) { 
				op2 = stack.pop(); 
				op1 = stack.pop(); 
				result = evalSingleOp(token.charAt(0), op1, op2); 
				stack.push(result); 
			} else { 
				stack.push(Integer.parseInt(token)); } }```

<u>Implementation of Stacks</u>

- Array-Based Implementation:
	- Fixed size; efficient for predictable sizes.

- Linked List Implementation:
	- Dynamic size; each node links to the next.

- Java-Specific Implementations:
	- `java.util.Stack`: Extends `Vector` (not recommended; violates stack purity)
	- Preferred alternatives:
		- `Deque`Interface: Use methods like `addFirst`,`removeFirst`, and `peekFirst`
		- `ArrayDeque`: Faster than `Stack` or `LinkedList`
		- `LinkedList`: Can function as a stack but includes extra overhead

<u>Efficiency Notes:</u>
- Access to stack elements (push, pop, peek): O(1)

- For maze traversal or expression evaluation, complexity depends on the problem size:
	- Maze: 
		- Let m= number of rows, n= number of collumns
		- A nested loop could iterate through all positions in the maze, leaidng to O(m * n) complexity