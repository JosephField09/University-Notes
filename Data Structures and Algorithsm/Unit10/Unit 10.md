MAP ADT:
- Maps keys to values

Typical operations includes:
- Add: Associate a new value with a new key
- Reassign: Associate an existing key in the map with a new value
- Remove: Remove a key with its associated value from the key set in the map
- Lookup: Find the value (if any) that is associated with a key

Maps useful for:
- model the contents of a dictionary
- model the contents of a phone book
- provide various indexing for a table of database records


<u>Map interface in JCF</u>

- java.util package includes the interface Map<K, V>.
- A map is a mapping from a finite set of keys to values.
- Each key is mapped to a single value.
- Given a key, one can look up the corresponding value from a map.
- New key-value pairs can be added to a map.
- Existing key-value pairs can be removed from the map.

- V get(Object key)
	- Returns the value to which the specified key is mapped

- V put(K key, V valye)
	- Associates the specified value with the specified key (Reassign)
	- If the key is not yet in the map, add a new key-value mapping. (Add)

- V remove(Object key) 
	- Removes the mapping for a key. (Remove)

Concrete implementations of Map<K, v> are:
- HashMap<K, V> - hash table implementation of map
	- Used when the order of the data in the map is irrelevant, e.g. for storing data in an electronic dictionary
- ConcurrentHashMap<K,V> - A thread-safe, hash table implementation of map that supports concurrent operations.
- TreeMap<K, V> - an ordered map, ordered by the natural order of keys
	- Used when the data in the map needs to be ordered


- Map does not extend the interface Iterable, so enhanced for statements can not be found

- Map provides convenient methods:
	- `Set<K> keySet`: Returns a set of the keys contained in this map.
	- `Set<Map.Entry<K,V>> entrySet`: Returns a set of key-to-value mappings contained in this map
	- `Collection<V> values:` returns a collection of the values contained in this map

