<u>Linked Structures</u>
- Use references to connect objects, forming dynamic and flexible data structures like:
	- Linked lists, stacks, queues and sets
- Unlike arrays, they can grow and shrink as needed
	- Makes them memory efficient but requires careful reference management


<u>Key concepts:</u>
- References as Links
	- A linked structure uses object references (pointers) to connect objects.
	- E.g. A `Person` object can reference another `Person` object as its's "mother"

- Self-Referential Objects
	- Classes like `Person` can include references to other objects of the same class, enabling hierarchical or linked data like family trees

- Nodes
	- A Node is the basic building block of linked structures
	- Each node contains:
		- Data (`element`)
		- Reference to the next node (`next`)

<u>Types of linked structure:</u>
- Linear Linked Structures
	- Singly Linked List:
		- Each node references only the next node
	- Doubly Linked List:
		- Each node references both the previous and the next node

- Non-Linear Linked Structure
	- Trees
		- Hierarchical structures with nodes having one parent (except the root)
	- Graphs
		- Nodes connected arbitrarily with potential cycles

<u>Operations on Linked Structures</u>
- Insertion
	- At the Front: 
		- Update the new node's `next` to point to the current head, then make it the new head
	- At the Middle:
		- Redirect the `next` reference of the preceding node to the new node

- Deletion
	- From the Front: 
		- Update the head reference to the second node
	- From the Middle:
		- Skip the node by adjusting references of the preceding and succeeding nodes

<u>Classes Implementing Linked Structures</u>

- Class `LinearNode<T>`
	- Represents a node in a linked list:
		- Stores an element of type `T`.
		- References the next node
	- Methods:
		- `getElement`/`setElement()`
		- `getNext()`/`setNext()`

- `LinkedStack`
	- Implements a stack using a linked list.
	- Operations:
		- `push`: Adds an element to the top
		- `pop`: Removes and returns the top element
		- `peek`: Retrieves the top element without removing it
	- Time Complexity O(1) for all operations.

- `LinkedQueue`
	- Implements a queue using a linked list
	- Keeps track of both the front and rear nodes
	- Operations:
		- `enqueue`: Adds element at the rear
		- `dequeue`: Removes element from the front
		- `first`: Retrieves the front element
	- Time Complexity O(1) for all operations.

- `LinkedSet`
	- Implements a set using a linked list
	- Operations:
		- `add`: Adds an element at the front (if not present)
		- `remove`:  Removes an element by searching and adjusting references
		- `contains`: Checks if an element exists
		- `union`,`intersection`,`difference`: Set operations
	- Time Complexity: O(n) for most operations (due to searching)

- `LinkedIterator`
	- Iterates over linked list elements
	- Tracks the current node using a `cursor`

<u>Advantages and Limitations</u>

- Advantages
	- Dynamic resizing
	- No wasted space due to pre-allocation (unlike arrays)

- Limitations
	- Additional memory for references
	- Operations like search are slow (O(n)) compared to arrays