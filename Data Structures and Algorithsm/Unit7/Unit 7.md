
An array-based implementation of the bounded queue ADT with the front of the queue fixed at index 0 has a drawback


circular queue
- A circular queue (or circular buffer) utilised an array that conceptually wraps around on itself
- Last index is thought to be followed by 0

- We track two integers for indication the front and the rear of the queue at any given time
- To distinguish between empty and full queues where front and rear are equal, we may record the size of the queue in count

- when an element is enqueued, it is stored at index rear.
	- rear is then incremented
- but we must allow for looping back to 0
	- rear = (rear + 1) % queue.length;

- with expandCapacity, existing elements are copied to the start of the enlarged array

- when an element is dequeued, it is retrieved from index front
	- front is then incremented

- queues are often used in multi-threaded software applications
- data items for processing are produced by 'producer' threads and deposited in a queue from where they are retrieved later by 'consumer' threads and processed.
	- if at a certain time, the producers are producing data faster than it can be consumed, the producers do not have to wait and they simply add their data items to the queue
	- when consumers start to consume data faster than it can be produced, they will not be delayed as they can retrieve data from the backlog in the queue.


<u>Priority queues</u>

- Most queues are FIFO but sometimes its useful for high-priority data to 'jump' the queue and join a queue ahead of lower priority data
- Data items of the same priority are still processed in a FIFO manner
- Priority of data items is represented by a range of non-negative integer values
	- 0 is the lowest priority up to a maximum priority value M
- A priority queue can be implemented used a linked list or an array
	- elements are ordered by priority level of the data items involved
- To enqueue an item means to insert it into a position in the list/array ahead of all lower priority items but behind data in terms of higher or equal priority

Array
![[Pasted image 20241028125120.png]]

linked structure
![[Pasted image 20241028125155.png]]

- Items can only be added to a priority queue if they have a priority level

- A simple array-based implementation of a priority queue is inefficient.
- A linked based implementation of priority queue is slightly better, but noy by much

- A multi-queue implementation:
	- Implement the priority queue as an array queueList of size M + 1 of ordinary FIFO queues 
	- An item is enqueued in the normal way on the FIFO queue corresponding to its priority level
	- Dequeue works by calling the dequeue method on the non-empty queue with the highest priority

![[Pasted image 20241028141057.png]]


- For the multi-FIFO queue implementation PriorityQueue, all queue operations are considered to execute in constant time


<u>Double ended queue</u>

- Deque can be used as a queue:

| Queue Method | Equivalent deque method |
| ------------ | ----------------------- |
| add(e)       | addLast(e)              |
| offer(e)     | offerLast(e)            |
| remove()     | removeFirst()           |
| poll()       | pollFirst()             |
| element()    | getFirst()              |
| peek()       | peekFirst()             |
- ArrayDeque is likely to be faster than LinkedList when used as a queue