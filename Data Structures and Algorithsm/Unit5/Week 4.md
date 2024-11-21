- A linked structure used object reference variables to link one object to another.
	- An object reference can be seen as a pointer to an object.

- An object can hold a reference to another object, even one in the same class.

```
public class Person {
	private Person mother;
	private String name;
	private boolean childBearing;
	private String address;
}
```

- The fundamental building blocks of a linked structure are self-referential objects:
	![[Pasted image 20241014122828.png]]
	- one object refers to another, which refers to another, etc.

- Each objects in the linked structure is known as a node.
- A linked structure is *dynamic* because its size may grow or shrink as needed
	- (unlike an array who's size is fixed)

- A linked structure can be linear or non-linear:
	- A **linked list** is a *linear* structure
		- Each node usually references to one or more other nodes.
	- **Trees** and **graphs** are both *non-linear* structure
		- Each node may make reference to less than one other node.

![[Pasted image 20241014124012.png]]

Tree
```
public class TreeNode {
	private TreeNode left;
	private TreeNode right;

	// ...

	public TreeNode(){
		left = null;
		right = null;
	}
}
```
Graph
```
public class GNode {
	private List<GNode> from;
	private List<GNode> to;

	// ...
}
```

- The *references* in a linked structure must be carefully managed to maintain the integrity of the structure.
- The *entry point* of `front` into the list *must* be maintained properly
- The *order* in which certain steps are taken is often very important

Inserting a node at the front of a linked structure

![[Pasted image 20241014141701.png]]

```
Node newNode = new Node();
newNode.setNext(front);
front = newNode;
```
Inserting a node in the middle of a linked structure

![[Pasted image 20241014141954.png]]

Deleting the first node in a linked structure

![[Pasted image 20241014142128.png]]


Deleting an interior node from a linked structure

![[Pasted image 20241014142225.png]]


Elements without inbuilt links

- Objects of classes naturally have links to objects of the same class and can easily be built into linked structures.

- A generic linear collection can store any one kind of object

```
public class LinearNode<T> {  
	private T element; // the element  
	private LinearNode<T> next; // the node which follows this node  
  
	public LinearNode() { // creates a standalone empty node  
		 next = null;  
		 element = null; }  
  
	public LinearNode (T elem) { // create a node with the given element  
		next = null;  
		element = elem; }  
  
	public LinearNode<T> getNext() {  
		 return next; }  
  
	public void setNext (LinearNode<T> node) {  
		 next = node; }  
  
	public T getElement() {  
 return element; }  
   
	 public void setElement (T elem) {  
		 element = elem;  
	}  
}  

```

Linked list implementation of a stack

- A stack is a linear collection whose elements are added and removed from one end

- A stack ADT can also be implemented using a linked list
- The LinkedStack class models a stack using a linked list
- A linked list is made up of a linear sequence of node objects

```
public class LinkedStack<T> implements StackADT<T>{
	private LinearNode<T> top;
	private int count;
}
```

- Method: push
	- Pushing an element into the stack means adding an element at the front of the linked list
	- ```
public void push (T element) {
	LinearNode<T> temp = new LinearNode<T> (element);

	temp.setNext(top);
	top = temp;
	count++;
}

- Method: pop
	- Popping an element from the stack means removing the first element in the linked list
	- ```
public T pop(){
	if (isEmpty())
		throw new IllegalStateException("Stack empty in pop")

	T result = top.getElement();
	top = top.getNext();
	count --;

	return result;
}

- Method: peek
	- Returns the object reference that is kept in the first node of the linked structure


- LinkedStack is an unbounded collection.
	- no need for expanding capacity
- Stack operations are generally efficient

- None of the LinkedStack operations require any loop.
	- Hence, all the stack operations can be performed in constant time



A Linked List Implementation of Queue

- A queue is a linear collection whose elements are added at one end and removed from another end.

- Using a linked list, there is no need for element shifting
- The last node in the queue has its next set equal to null

- A linked list implementation is more flexible than an array
	- The size of the queue can grow and shrink as required at run-time
- No storage space wasted creating initial storage for the cells in an array
- There is no need to check in enqueue if the queue is already full

- However every node contains 2 references compared to an array element which contains only 1
	- There are extra storage overheads for queue given size



A linked List implementation of a Set

- A set is a collection of distinct elements of a particular type
- A set is logically an unordered collection, with each element is unique

- Using a linked list we will implement a set class named LinkedSet

- We may need to remove elements from the middle of the linked list.
- New elements will always be added at the start of the list

- As with ArraySet, this class will extend AbstractSet where some methods of setADT (e.g. addALl and removeAll) are implements in terms of add and remove

```
public class LinkedSet<T> extends AbstractSet<T> {
	private int count; // the current number of elements in the set.
	private LinearNode<T> contents; // the first node in the linked set

	public LinkedSet() {
		count = 0;
		contents = null;
	}

	public voolean isEmpty() {
		return contents == null;
	}

	public int size() {
		return count;
	}

	public void clear() {
		contents = null;
		count = 0;
	}
}
```

- Method: contains

```
public boolean contains(T element){
	LinearNode<T> current = contents;
	while (current != null) {
		if (element.equals(current.getElement())){
			return true;
		}
		else {
			current = current.getNext();
		}
	}
	return false;
}
```

- Method: removes
	- Remove the first node in the linked list
		 or
	- Remove an interior node from the linked list

- Method iterator:
	- To complete the implementation of LinkedSet, we need to define an iterator method as the class implements the iterable 

	- Creates a new type of iterator object to handle iteration over this LinkedSet object
	- A LinkedIterator object specialises in iterating over a linear linked structure
