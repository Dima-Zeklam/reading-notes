# Hash Tables
Hash Tables is a data structure used to store keys/value pairs, also Hash Tables is the ability to store the key into this data structure, and quickly retrieve the value.
![Hash Tables](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7d/Hash_table_3_1_1_0_1_0_0_SP.svg/1200px-Hash_table_3_1_1_0_1_0_0_SP.svg.png)

* **Hash** : In hashtable, it is used to determine the index of the array.

*  **buckets** are used to apportion data items for sorting or lookup purposes.

* **Collisions** is what happens when more than one key gets hashed to the same location of the hashtable.

* **Hashing** is a technique that is used to uniquely identify a specific object from a group of similar objects.

## Hash function
The hash function converts the item into a small integer or hash value. This integer is used as an index to store the original data, is important to have a good hash function with the following basic requirements:
1. Should be easy to compute 
2.  never gets stuck in clustering and distributes keys evenly across the hash table.
3. Avoid collisions which occur when pairs of elements are mapped to the same hash value.

Hashing uses unique index to perform insert, update, and search operations.

### Collision Resolution Techniques
*  The collision creates a problem because each index in a hash table is supposed to store only one value. 
* Hashing in data structure falls into a collision if two keys are assigned the same index number in the hash table. 

### Hash table Complixity
* If too many elements were hashed into the same key: looking inside this key or Once a hash table has passed its load balance - it has to rehash may take O(n) time.
* if you chose a good hash function and you don't have too big load balance it is said to be O(1) average case.
* Create a new bigger table, and re-insert each element to the table it well take O(n) time.


### Advantages of Hashing
The main advantage of hash tables over other data structures is speed. The access time of an element is on average O(1), therefore lookup could be performed very fast. Hash tables are particularly efficient when the maximum number of entries can be predicted in advance.

### disadvantages of Hash table
The disadvantages of hash tables include the fact that databases can degrade if they go through a large number of collisions. The probability that a collision will occur increases with the amount of data. A large number of hash functions do not have the ability to move to the next or previous data set.


### For more information read [Hash table](https://en.wikipedia.org/wiki/Hash_table) and Watch [what is a hash table?](https://www.youtube.com/watch?v=MfhjkfocRR0). 