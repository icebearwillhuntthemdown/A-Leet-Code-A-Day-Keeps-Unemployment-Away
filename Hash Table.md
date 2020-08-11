# Hash Table

A data structure consists of **key and value** and uses the key instead of index. The key input goes into a 'hash function' which returns a hash code which is the memory address corresponding to the key to access the value. Many languages have their own built in hash table, for example, maps in Java, object in JavaScript, and dictionaries in Python.  

##### What does 'Hash' mean?
> The term "hash" comes by way of analogy with its non-technical meaning, to "chop and mix". Indeed, typical hash functions, like the mod operation, "chop" the input domain into many sub-domains that get "mixed" into the output range to improve the uniformity of the key distribution.

## Big O
* Insertion : O(1)
* Deletion : O(1)
* Lookup : O(1)
* Search : O(1)
  
**Pros**
* Fast lookups
* Fast inserts
* Flexible keys  
+) Hash tables are usually the answer to improve time complexity  
Fast Access O(1), but trades off with more memory O(n)  

**Cons**
* Unordered
* Slow key iteration  

### Hash Collision
Despite the good performance shown above, hash tables also have downsides and 'hash collision' is one of them. Hash collision refers to the situation where the hash function generates the same hash result for different hash String or key. As hash table allocates data randomly depending on the hash result, this brings about uneven memory usage and accumulation on certain memory locations which slows down the process to O(n).





[HashTable, HashMap, and HashSet](https://stackoverflow.com/questions/47838841/hashtable-hashmap-hashset-hash-table-concept-in-java-collection-framework)
