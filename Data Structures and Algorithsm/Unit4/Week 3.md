
Abstract classes:
- Achieve improved modularisation 
- Foster reuse

- We can use an abstract class to group all common methods

addAll:

- to add all elements in the given set into this set objecy

`public boolean addAll(SetADT<T> A) {`  
	`boolean hasBeenModified = false;`  
	`for (T element : A) {`  
		`if (this.add(element)) {`  
			 `hasBeenModified = true;`  
		`}`  
	`}`  
	`return hasBeenModified;`  
`}`

- iterates through the elements of set A adding its elements one by one
- If at least one element of A is added to the set, we update the value of `hasBeenModified` to `true`.

removeAll:

- To remove all elements in the given set from this set object

`public boolean removeAll(SetADT<T> A) {`  
	`boolean hasBeenModified = false;`  
``  
	`Iterator<T> iter = A.iterator();`  
	`while (iter.hasNext()) {`  
		`if (this.remove(iter.next())) {`  
			`hasBeenModified = true;`  
		`}`  
	`}`  
``  
	`return hasBeenModified;`  
`}` 

- We iterate through the elements of set A and attempt to remove them from the current set one by one using remove

retainAll:

- Remove all elements except the ones in the given set

`public boolean retainAll(SetADT<T> A) {`
	`boolean hasBeenModified = false;`
	`Iterator<T> iter = this.iterator();`
	`while (iter.hasNext()) {`
		`if (!A.contains(iter.next())) {`
			`iter.remove();`
			`hasBeenModified = true;`
		`}`
	`}`
`}`

isSubset:

- Checks if set is a subset of another

`public boolean isSubset(SetADT<T> A) {`  
	`if (this.size() > A.size()) {`  
		`return false;`  
	`}`  
	`for (T element : this) {`  
		`if (!A.contains(element)) {`  
			`return false;`  
		`}`  
	`}`  
	`return true;`  
`}`

- in most implementations, size is likely to execute in constant time
- checks that set is not larger than A before entering the while loop.

Equals:

- To check whether the given set contains exactly the same elements as this object 

`public boolean equals(SetADT<T> A) {  
	`if(this.size() != A.size()) {`  
		`return false;`  
	`}`  
	`return isSubset(A) && A.isSubset(this);`  
`}`

- As a simple optimisation in equals, we first check whether the sizes of the two sets are equal.


Declaring Arrays
- Once storage for an array has been allocated, the array has a fixed capacity
- arrays elements can be of any java type

`int[]a;`
`a = new int[10];`

`double[] b = new double[20];`

`boolean[] attendanceInAWeek = new boolean[5];`

- Storage for an array object can be allocated and initialised using an array aggregate, e.g:
	` int[] c = {5, 2, 1, 4};`
- Array aggregates can only be used when an array variable is declared, they cannot be used to initialise arrays.

- the number of elements in an array can be accessed using the `final` field `length` of the array
- more convenient to use an enhanced `for` loop

- Access to array elements is fast - O(1).
- Processing a while 1-D array of size n involves a loop being executed n times
	- time complexity of the whole process is O(n)


ArraySet:

- An array based-implementation of SetADT

![[Pasted image 20241007142254.png]]

`import java.util.Iterator;`
`public class ArraySet<T> extends AbstractSet<T> implements Bounded`
`{`
	`private static final int DEFAULT_CAPACITY = 100;`

	`private T[] contents;`
	`private final int maxSize;`
	`private int currentSize;`

	//Constructor method 1
	@Suppress Warnings("Unchecked")
	public ArraySet(int maxSize) {
		contents = (T[]) (new Object[maxSize]);
		currentSize = 0;
		this.maxSize = maxSize;
	} //An object is created and then converted to T[] by type casting
	
	public ArraySet() {
		this(DEFAULT_CAPACITY);
	} 


	//Constructor method 2
	@SuppressWarnings("unchecked")
	public ArraySet (int maxSize) {
		contents = (T[])
			Array.newInstance(Object.class, maxSize); //2
		currentSize = 0;
		this.maxSize = maxSize;
	} //Array.newInstance is a class method in java.lang.reflect.Array.
	// No need to create an Array objec to invoke it

	public ArraySet() {
		this(DEFAULT_CAPACITY);
	}
`}`

Basic Accessor Methods:
- size()
- isEmpty()
- capacity()
- isFull()


contains:
- searched the array to see if the element is present.
	- if so, it returns true as soon as element is found

`public boolean contains(T element) {`
	`for (int i=0; i < currentSize; i++) {`
		`if (element.equals(contents[i]))`
			`return true;`
		`}`
		`return false;`
`}`

- An enhanced for loop uses an Iterator which slows down things behind the scenes, so a regular for loop is used

add:
- Use contains to check whether the element is already in the set.
	- If so, returns false and leaves the set unaltered

- If the element is not present, adds the element to the end of the array and returns true to indicate the set has been modified.

`public boolean add(T element){`
	`if (!contains(element)) {`
		`if(!isFull()) {`
			`contents[currentSize] = element;`
			`currentSize ++;`
			`return true;`
		`} else {`
			`throw new`
			   `IllegalStateException("Set full in method add");`
		`}`
	`} else {`
		`return false;`
	`}`
 `}`


remove:
- searches the array to see if the elements is present.
- If it finds the element at index i, it overwrites it with the last element without leaving a gap

`public boolean remove(T element) {`
	`for (int i=0; i < currentSize; i++){`
		`if (element.equals(contents[i])){`
			`currentSize --;`
			`contents[i] = contents[currentSize];`
			`return true;`
		`}`
	`}`
	`return false;`
`}`


intersection:

`public SetADT<T> intersection (SetADT<T> A){`
	`//create a new empty set to hold result`
	`ArraySet<T> result = new ArraySet<T>(maxSize);`

	`for (int i = 0; i < currentSize; i++) {`
		`// Go through each element of this set.`
		`// If this element is also in A, add it to 'result'.`
		`if (A.contains(contents[i])) {`
			`result.contents[result.currentSize] = contents [i];`
			`result.currentSize++;`
		`}`
	`}`
	`return result;`
`}`


Iterators:

- to complete the implementation of ArraySet, we need an iterator as the class implements the java.lang.Iterable interface
- An iterator is an object that allows the user to acquire and use each element of a collection in turn.
- Method iterator returns java.util.Iterator object

- An Iterator object has methods:
	- hasNext:
		- returns true if there are more elements in the iteration
	- next:
		- returns next element in the iteration
	- default remove:
		- removes the current element of the collection
	- defailt forEachRemaining

implement Iterator() method:

`import java.util.Iterator;`

`public class Box<X> implements Iterable<X> {`
	`private ArrayList<X> contents;`
	
	// Other definitions and method details omitted.

	public Iterator<x> iterator() {
		return contents.iterator();
	}
`}`

- We define a new class ArrayIterator and use it whenever we need to iterate over any array-based collection

`import java.util.Iterator;`  
`public class ArrayIterator<T> implements Iterator<T> {`  

	`private T[] contents; // the elements to be iterated over`  
 
	`/* the index of the element to be returned`  
		`in the next() operation */`  
	`private int cursor;`  
  
	`private int limit;`  
  
	`public ArrayIterator(T[] array, int size) {`  
		`contents = array;`  
		`limit = size;`  
		`cursor = 0;`  
	`}`  
  
	`// other method definitions: hasNext(), next(), remove()`  
`}`

Iterator methods:

`public boolean hasNext() {`
	`return cursor < limit;`
`}`

`public T next() {`
	`if (!hasNext()) {`
		`throw new`
		`IllegalStateException("ArrayIterator: no next element.");`
	`} else {`
		`return contents[cursor++];`
				`// the increment is done afterwards`
	`}`
`}`

`public void remove() {`
	`throw new`
		`UnsupportedOperationException("ArrayIterator: remove");`
`}`


```
iterator() in Class ArraySet:

public class ArraySet<T> extends AbstractSet<T> {`
	// definition of fields omitted`

	`/* definition of constructors and` 
		`other methods omitted */`

	`public Iterator<T> iterator() {`
		`return new ArrayIterator<T>(contents, currentSize);`
	`}`
`}`

```

- iterator in ArraySet simply creates a new ArrayIterator object and returns it.


Implementing an Unbounded Collection using Array:

- When the array reaches its capacity, we can expand it by creating a new, larger array and copy the current items to the new array.

```
private T[] contents; // an array for the stack elements

	//other details omitted

	@SuppressWarnings("Unchecked")
	private void expandCapacity() {
		// Create a new, larger array.
		T[] larger = (T[]) (new Object [contents.length*2]);
		// Copy elements in the old array to the new array.
		for (int index=0; index < contents.length; index++){
			larger[index] = contents [index];
		}
		// Update the contents using the new array.
		contents = larger;
	}
```
- When adding an element to an unbounded set, we may need to expand the capacity of contents:

```
public boolean add(T element){
	boolean added = false;
	if (!contains(element)) {
		if (size() == contents.length) {
			expandCapacity();
		}
		contents[currentSize] = element;
		currentSize++;
		added = true;
	}
	return added;
}

```

A bounded stack Implementation

- An array-based implementation leads to a bounded collection as the collection will have a maximum size.
- Stack grows upwards from the start of the array as items are pushed onto it


```
public class ArrayStack<T> implements BoundedStackADT<T>{
	private static final int DEFAULT_CAPACITY= 100;

	// an array to hold the stack elements
	private T[] contents;
	// maximum capacity of the stack
	private final int maxSize;
	private int top; // its current size

	/** Constructs a new empty stack */
	public ArrayStack(){
		this(DEFAULT_CAPACITY);
	}

	/** Constructs a new empty stack with the specified capacity. */
	public ArrayStack(int maxSize) {
		contents = (T[])(new Object[maxSize]);
		top = 0;
		this.maxSize = maxSize;
	}

	public int size(){
		return top;
	}

	public boolean isEmpty() {
		return (top == 0);
	}

	public int capacity() {
		return maxSize;
	}

	public boolean isFull() {
		return (top == maxSize);
	}

	public void push(T element) {
		//check if the stack is full
		if (top == maxSize) {
			throw new IllegalStateException("Stack full");
		}
		contents[top] = element; // add the element
		top++; //increase the size by 1
	}

	public T pop() {
		// check if the stack is empty
		if (top == 0) {
			throw new IllegalStateException("Stack empty");
		}
		top--; // decrease the size of the stack by 1
		return contents[top]; // return elements at the top
	}

	// similar to pop ut without removing the element from the stack
	public T peek() {
		// check if the stack is empty
		if (top == 0){
			throw new IllegalStateException("Stack empty");
		}

		// return element at the top
		return contents[top - 1];
	}

	// clear sets the top of the stack to 0
	public void clear() {
		top = 0;
	}
}
```
- ArrayStack is bounded
- None of the methods in ArrayStack involves any looping constructs 
- All (push, pop, peek, size, clear) will execute in constant time T(n) = O(1)


- The only difference between an array implementation of a bounded and an unbounded stack is the push operation.

```
	public void push(T element) {
		//check if the stack is full
		if (size() == contents.length) {
			// expand the storage capacity
			expandCapacity();
		}
		contents[top] = element;
		top++;
	}
```
- There is no need to throw an `IllegalStateException`


A bounded queue:

- contents of a queue can be managed using an array in which index 0 represents  the front.
- We can define an int variable rear to keep an integer value that represents:
	- the next available slot in the array (i.e. the cell that is not currently used for keeping an object reference), and
	- the number of elements currently in the queue

```
public class ArrayQueue<T> implements QueueADT<T> {
	private static final int DEFAULT_CAPACITY = 100;
	private int rear; // the next available slot
	private T[] queue;


	//An empty queue means that no element is in the array
	public ArrayQueue (int initialCapacity){
		rear = 0;
		queue = (T[])(new Object[inititalCapacity]);
	}

	// to enqueue means to assign the object reference of the adding element to the read of the queue
	// also need to update the value of rear

	public void enqueue (T element) {
		if (size() == queue.length)
			throw new IllegalStateException("Queue full in enqueue");
			queue[rear] = element;
			rear++;
	}

	// to dequeue means that the object reference that is kept in the array cell with the index 0 is needed to be removed.
	// all other elements within the queue are needed to be shifted also.

	public T dequeue() {
		if (isEmpty())
			throw new IllegalStateException("Queue empty in dequeue");
		T result = queue[0];
		rear --;
		/* shift the elements */
		for (int scan=0; scan < read; scan++)
			queue[scan] = queue[scan+1];
		queue[rear] = null;
		return result;
	}
}
```
