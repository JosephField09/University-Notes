- A singly linked list has one reference in each node.
	- Each node knows its follower node
	- ![[Pasted image 20241118121446.png]]

- A doubly linked list has two references in each node:
	- Previous and next
	- Each node knows its previous node and its follower node
	- ![[Pasted image 20241118121459.png]]
- Advantages:
	- Each node of a doubly linked list has a reference to both the next and previous nodes in the list.
		- We can easily move backwards and forwards
	- You can choose to traverse the linked list in reverse order.
	- It is also easier to support the remove operation of an Iterator over a doubly linked list

- Disadvantages:
	- There are increased storage overheads
		- Each node now contains three reference fields
	- More 'book-keeping' is now required to manage the links in doubly-linked list operations e.g.:
		- Insertion and removal of nodes in the middle of a linked list both require modifications to the previous node

- <u>Recap on issue with class LinkedIterator</u>
	- Linked Iterators keep track of the current node only, which means it has no means to support the remove method 
	- This is because the next node has no way of knowing what node came before the one that it is removing, with a doubly list, the previous and next are stored

- To model a doubly linked list we define:
	- DoubleNode: 
		- to model a node within a doubly linked list
	- An abstract class DoubleList:
		- to model a doubly linked list
		- Will be used as the basis on which to build various doubly linked linear structures such as an ordered set, an ordered list and an indexed list
	- An inner class DoubleIterator: to provide an iterator for a doubly linked list.
		- Unlike LinkedIterator, DoubleIterator will support the remove operation

![[Pasted image 20241118123427.png]]

- Class DoubleList is abstract
	- Instances of DoubleList cannot be created
- Unusually, all the methods of this abstract class are concrete
	- This is to ease the burden on implementations of extensions of the class
- Most of the methods of this class are protected
	- They are not inteded to be used by general client code, but rather are utility methods to be used by implementers of various collection ADTs
- We will use this class to implement some useful collection ADTs such as ordered lists and indexed lists
- The simpler methods such as isEmpty and size are public and may be called by client code directly
- Three protected data fields: count, front & rear


<u>An iterator for Doubly-Linked Lists</u>
- This iterator will support the remove operation
- The remove method should be able to remove from the collection the item returned by the last call to next.
- It should not be possible to:
	- Call remove before next is called, or
	- To call remove twice without intervening call of next
- In order to implement remove, the iterator class needs to have access to all data fields in DoubleList
	- Make DoubleIterator an inner class of DoubleList
- DoubleIterator is nested in generic class `DoubleList<T>`. So it is simplicitly generic, and `<T>` must not appear in its header


<u>Abstract Data Type: Lists</u>
- Lists are linear collections
	- Lists are more flexible than stacks or queues
- Elements can be added or removed anywhere within a list
- Two types of list collections:
	- Ordered (or sorted) lists
	- Indexed lists

<u>Ordered and indexed lists</u>
- Elements in an ordered list are ordered by some inherent characteristic of the elements
	- e.g. alphabetical, ascending, chronological
- In an indexed list, elements are referenced by their numerical position or index in the list
	- There is often no inherent order relationship among the elements
- ![[Pasted image 20241118152607.png]]
<u>List Operations</u>
![[Pasted image 20241118153108.png]]

<u>OrderedListADT</u>
- Has one new method: add(T element)
- To belong to an ordered list, elements must have a natural order
- If objects in a class are expected to have an inherent order, the class must implement the standard java interface
	- `java.lang.Comparable<T>`
- This interface specifies a single method compareTo:
	- `int compareTo(T obj);`
	- <0 : this object should precede the given object obj
	- =0: this objects has the same natural order as obj
	- >0: this object should come after the given object obj
- To ensure that the type used to instantiate the generic interface has an inherent order, we must qualify the generic parameter:
	- `< T extends Comparable<T> >`
- `remove` uses `find` to locate the node containing the element to remove, if it is present. It then uses the `remove` method of super-class `DoubleList` to remove it.
- `add` searches through the list to locate where the new node should be added. It then uses the `addBefore` method of `DoubleList` to add it
- `removeLast` simply uses `removeLast` of the super-class `DoubleList` to remove it


<u>Using an ordered list</u>

- Within an ordered list, elements are ordered by their inherent order.
	- The knowledge of ordering is defined within the element itself
- Some objects have **natural order**, e.g. `Employee`, `Car` and `Ticket` objects, we can introduce an order by explicitly defining it in the class definition

<u>IndexedListADT </u>

- `Linked IndexedList`:
	- `get`returns the element in node returned by `findNode`
	- `set`locates the $i^th$ node using `findNode`, changes the element stored in the node and then returns the old element
	- `remove` locates the $i^th$ node using `findNode`, then removes the node using `super.node` and returns the element.
	- `add` checks the index for the special cases of addition at the front or the end of the list and calls `addFront`or `addLast`as appropriate.
		- It then uses `findNode` to locate the $i^th$ and uses `addBefore`to add a new node before the current $i^th$ node.

<u>Implementing Lists with Arrays</u>

- An array implementation of a list could follow strategies similar to those used for a queue
- We could fix one end of the list at index 0 and shift as needed when an element is added or removed.

- Due to the indexed nature, array is a natural choice for implementing an indexed list.
- Elements are kept continuously at one end of an array
- An integer variable(`size`) stores the number of elements in the list, and is also the index of the *first empty cell* in the array.
- In order to allow the list to grow *indefinitely*, we will need to perform "expand capacity"
- An integer variable (`capacity`) holds the current size of the underlying array used to store the elements of the list

- When the array is extended, the elements of the old array are copied to the new array *leaving a gap* at position `gap`
	- Thew new element can be added without any further element shifting
	- On average this saved n/2 assignments whenever the underlying array is extended


- `ArrayList: iterator`
	- The iterator is implemented using an *inner class* and now supports the `remove`operation 
	- This new version of `ArrayIterator`:
		- may access the private fields of `ArrayList`
		- does not require any parameter, and
		- supports the remove operation

<u>An array implementation of an ordered list</u>

- It is convenient to base the implementation of `OrderedArrayList`on that of `ArrayList`.
	- `ArrayList` is practically an indexed list
	- If we simply extend the class `ArrayList`; we will inherit too many methods
	- Inheriting methods such as *add element as index* and *set element at index* in class `ArrayList` would be very likely to violate inherent ordering of the ordered list.

- We could define an abstract class implementing the common operations of indexed and ordered lists and then extend this.
	- Would lead to a more complex class hierarchy 

- A better way would be to reuse an existing class, but restrict the available operations that can be performed
- We hide an instance of the existing class as a private field of the new class
- Provide *'wrapper'* methods to call only those methods of the hidden class which is it safe for clients to use.
	- Same approach used in class `PureStack`

