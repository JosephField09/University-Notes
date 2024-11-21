Hash tables - apart of implementations group

Hash function:
	- For computing the location of an element in a hash table

Cell/Bucket:
	- A storage location in the hash table

Hashing:
	- A computing process to determine the location where an element will be (or is) stored in a hash table

Hash value:
	- A value computed from a hash function, 
	- i.e. the index of the location in which an element is to be stored within a  hash table

- Time complexity is O(1)

- Collision occurs when two elements try to get mapped to the same bucket.
- Perfect hash function has no collision 

<u>Hashing method- Extraction</u>

- E.g. :
	- Create a hash table with 26 cells
	- Each cell will store one name that begins with different letter
	- We create a simple hash function that used the first letter of each name
	- Array will look like:
		- ![[Pasted image 20241111123645.png]]
		- Method to work out would be using the ASCII code to know its location
			- use the formula: indeex = ASCII.code - 65
			- e.g. 67-65 = 2 (C)

<u>Hashing Method - Division</u>

- E.g. : 
	- Assume we are to create a hash table with 50,000 cells
	- Each cell will store one Aston Uni student record
	- We create a hash function as follows:
		- hashValue(key) = |key| mod p
	- where:
		- key is the candidate number of a student
		- p can be the size of the hash table (num of buckets)


<u>Hashing</u>

- All operations on an element of a hash table should be O(1) …theoretically
- This efficiency can only be realised if each elements maps to a unique position in the table
- A collision occurs when >= 2 elements map to the same location
- A hash function that maps each element to a unique location is called perfect hash function

<u>Resolving collisions: Chaining</u>

- Need to resolve a collision to:
	- A perfect hash function is not easy to develop
	- We often dont know size of dataset 
	- We need a method to handle collisions, e.g. chaining

- The chaining method:
	- Treats each cell in the hash table conceptually as a collection
	- Two implementations:
		- Using a linked stricture:
		- ![[Pasted image 20241111142011.png]]
		- Or using an array based structure with an overflow area
		- ![[Pasted image 20241111142022.png]]



<u>How large should the table be?</u>

- If dataset is of size n and we have a perfect hash function, the table should be size n
- Without a perfect hash function, but we know that the size of the dataset is n, the rule of thumb is to make the table 150% of the size of the dataset
- If we don't know the size of the dataset, we will depend upon dynamic resizing

- Resizing a hash table dynamically means to:
	- Create a new, larger hash table
	- Insert all of the entries of the old table into the new one, and
	- Rehash the entries

- Deciding when to resize is important to dynamic resizing:
	- We can simply resize when the table is full
	- A better approach is to use a load factor
		- The load factor of a hash table is the percentage occupancy of the table at which the table will be resized
		- e.g. a hash table with a load factor of 75% will resize when it is 75% full

<u>Working with hash functions</u>

- A hash function is typically use part of the object information (i.e. the key) to get the hash value
- Extraction involves using only a part of an element's value (or key) to compute the location at which to store the element
- Division used the remainder of the key divided by some positive integer, p, as the index of element
- A good hash function should assign an element to a cell in a random manner 


<u>Need for hashing:</u>

- Items can be looked up in constant time
- Items can be added in constant time
- Prevents the need for reserving $10^13$ storage spaces for values likely to not appear in the collection

<u>Hash Functions in java</u>

- In java, an object's hash code is used to determine where to put the object in a hash table
	- identical objects, as indicated by the method equals, must have the same hash code
- Output of a hash function indicated where an element is (to be) stored within the hash table

- Two String objects having exactly the same sequence of characters will be treated as identical objects

- Hashtable<K,V>: Implements a hash table, mapping keys to  
values.  
- HashMap<K,V>: Hash table based implementation of Map.  
- HashSet<V>: Implements Set, backed by a hash table.  
- LinkedHashSet<K,V>: A hash table and a linked list  
implementation of Set.  
- LinkedHashMap<K,V>: A hash table and a linked list  
implementation of Map.  