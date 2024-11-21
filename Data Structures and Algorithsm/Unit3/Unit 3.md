[[Data Structures and Algorithms]]

An abstract Data Type is a mathematical specification of:
 - A set of data, and
 - the set of operations that can be performed on that data

Such a data type is abstract as the focus is on defining the properties of the of date and the behaviour of the operations that act on it.
- The same ADT can be implemented in various ways
- Users/Clients are not informed about how the data type is actually implemented


For each ADT, we specify two pieces of information:
- The abstract structure of the data, and
- the typical operations that can be performed on the data.


- A collection is an object that represents a group of objects of some fixed type.
- They can be broadly categorised at:
	- unordered
	- linear
	- non-linear

- The elements within a collection are usually organised based on:
	- the order in which they were added to a collection
	- some inherent relationship among the elements themselves
		- e.g. Numeric order, Alphabetical Order, Chronological order

- Bounded collections are collections that has a maximum size/capacity

- Unbounded collections is when there is no limit on the size of the collection



- Exception in java means to handle the situation when a problem arises during the program's execution.

- When working with an exception, the caller program can:
	- Handle the exception, or
	- Not handle the exception, simply pass it (propagate it) to the program's caller


- You can hide implementations using an interface
	- A well-defined interface masks the implementation of the collection



Stacks
- A stack is a linear collection
- Elements are added and removed from one end
- LIFO: Last In, First Out
- Usually depicted vertically

- Push: Add an element to the top
- Pop: Remove the element at the top and return it
- Peek: Return element on the top without removal

- Regular stack is unbounded
- To bound it, we need to add extra operations of isFull and capacity


Queues
- A queue is a linear collection that has opening at both ends
- FIFO: First In, First Out
- Elements removed same order they are added

- Operations occur at both ends (Front and Back)
- Usually depicted horizontally
- Elements are added at the rear (tail) of the queue
- Elements are removed from the front end (head) of the queue

- Enqueue: adds an element to the tail of a queue
- Dequeue: removes an element from the head of the queue
- Size: Returns number of elements in the queue

- A pure queue does not allow access to the elements in the middle


Lists
- Also known as sequences
- Linear collection
	- Move flexible than stacks or queues
- Elements can be added or removed anywhere within a list
- A list may contain duplicate values
- Different types of lists

- removeFirst: Removes first element from the list
- removeLast: Removes last element from the list
- remove: Removes specific element from the list
- first: Returns the first element of the list
- last: Returns the last element of the list
- contains: Checks whether a specified element is on the list
- isEmpty: Checks whether the list is empty
- size: Returns the number of elements on the list.


Non - Linear Collections

Map:
- a.k.a dictionary, associative array, lookup table
- Maps keys to values
- Each key is associated with one value
- Typically each key in a map is unique
	- Different keys may be mapped to the same value

- Add: Add a new key-value mapping to the map
- Reassign: Associate an existing key with its associated value from the key set in the map.
- Remove: Remove a key with its associated value from the key set in the map
- Lookup: Find the value that is associated with a key


Set:
- A set is a collection of distinct elements of a particular type.
- Elements in a set are unordered
	- Elements may be ordered for efficiency
	
- All elements in a set must be unique

- isEmpty; determines whether a set is empty
- size: determine the number of elements
- add: add specified elements to the set
- remove: remove specified elements from the set

- removeAll: removes every element from a set except a set of specified elements
- contains: determins if an element is apart of a set
- equals: determines if two sets have the same members
- isSubset: determine if a set is a subset of another

- union of sets A and B - contains all the elements of A and B

- intersection of sets A and B - contains only those that are members of both A and B

- difference of sets A and B - contains all the elements of A that are not members of B

- pick - select a random element of a set without removing it

- removeRandom operation to select and remove a randomly chosen element from a set

- iterator method - process each element in the set



Multi-set:
-  generalisation of the set concept in which the same element may appear more than once.
- operations are similar, but they take proper account of duplicate elements.

- two multi-sets are equal if they contain exactly the same elements with duplicate elements appearing the same number of times in each.
- isSubbag is true if every element of A occurs at least as many times in B as it does in A

- if an element occurs n times in ulti-set A and m times in multi-set B, then:

	- Union - it occurs max(n,m) times

	- Intersection - it occurs min(n,m) times

	- Difference - it occurs max(0,(n-m)) times

- count: returns the number of occurrences of a specified element in the multi-set.

- sum: if an element occurs n times in multi-set A and m times in multi-set B then it occurs (n+m) times in A + B