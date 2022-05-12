# Collections Interview Questions and Answers


## Q. What is difference between Comparable and Comparator interface?
**Comparable**: A comparable object is capable of comparing itself with another object. The class itself must implements the `java.lang.Comparable` interface in order to be able to compare its instances.

**Comparator**: A comparator object is capable of comparing two different objects. The class is not comparing its instances, but some other class’s instances. This comparator class must implement the `java.util.Comparator` interface.

Comparable and Comparator both are interfaces and can be used to sort collection elements.

| Sl.No|Comparable	         |Comparator                                                |
|------|-----------------------|----------------------------------------------------------|
| 01.|Comparable provides a single sorting sequence. In other words, we can sort the collection on the basis of a single element such as id, name, and price.|The Comparator provides multiple sorting sequences. In other words, we can sort the collection on the basis of multiple elements such as id, name, and price etc.|
| 02.|Comparable affects the original class, i.e., the actual class is modified.|Comparator doesn't affect the original class, i.e., the actual class is not modified.|
| 03.|Comparable provides compareTo() method to sort elements.|	Comparator provides compare() method to sort elements.|
| 04.|Comparable is present in java.lang package.|A Comparator is present in the java.util package.|
| 05.|We can sort the list elements of Comparable type by Collections.sort(List) method.|We can sort the list elements of Comparator type by Collections.sort(List, Comparator) method.|


## Q. What is difference between HashMap and Hashtable?
HashMap and Hashtable both are used to store data in key and value form. Both are using hashing technique to store unique keys.

|Sl.No|HashMap	              |Hashtable                                         |
|-----|-----------------------|--------------------------------------------------|
| 01. |HashMap is **non synchronized**. It is not-thread safe and can't be shared between many threads without proper synchronization code.|Hashtable is **synchronized**. It is thread-safe and can be shared with many threads.|
| 02. |HashMap allows one null key and multiple null values.|Hashtable doesn't allow any null key or value.|
| 03. |HashMap is a new class introduced in JDK 1.2.|Hashtable is a legacy class.|
| 04. |HashMap is fast.       |Hashtable is slow.|
| 05. |We can make the HashMap as synchronized by calling this code Map m = Collections.synchronizedMap(hashMap);|Hashtable is internally synchronized and can't be unsynchronized.|
| 06. |HashMap is traversed by Iterator.	|Hashtable is traversed by Enumerator and Iterator.|
| 07. |Iterator in HashMap is fail-fast.	|Enumerator in Hashtable is not fail-fast.         |
| 08. |HashMap inherits AbstractMap class.	|Hashtable inherits Dictionary class.              |


## Q. What is difference between Enumeration and Iterator interface?
Enumeration and Iterator are two interfaces in java.util package which are used to traverse over the elements of a Collection object.

**Differences**  

|Iterator	|Enumeration         |
|-----------|--------------------|
|hasNext()	|hasMoreElements()   |
|next()	    |nextElement()       |
|remove()	|(Not Available)     |


| Sl.No |Enumeration	             |Iterator                          |
|-------|----------------------------|----------------------------------|
| 01.  |Using Enumeration, you can only traverse the collection. You can’t do any modifications to collection while traversing it.    |Using Iterator, you can remove an element of the collection while traversing it.|
| 02.  |Enumeration is introduced in JDK 1.0|	Iterator is introduced from JDK 1.2     |
| 03.  |Enumeration is used to traverse the legacy classes like Vector, Stack and HashTable.|Iterator is used to iterate most of the classes in the collection framework like ArrayList, HashSet, HashMap, LinkedList etc.|
| 04.  |Methods : hasMoreElements() and nextElement()|	Methods : hasNext(), next() and remove()|
| 05.  |Enumeration is fail-safe in nature.	|Iterator is fail-fast in nature.|
| 06.  |Enumeration is not safe and secured due to it’s fail-safe nature.|	Iterator is safer and secured than Enumeration.|


## Q. What is the difference between Set and Map?

**Sets**:-

1. Set does not  allow duplicates. Set and all of the classes which implements Set interface should have unique elements.
2. Set allows single null value at most.
3. Set does not  maintain any order; still few of its classes sort the elements in an order such as LinkedHashSet maintains the elements in insertion order.
4. Classes used in sets are Set: HashSet, Linked HashSet, TreeSet, SortedSet etc.

**Maps**:-

1. Map stored the elements as key & value pair. Map doesn’t allow duplicate keys while it allows duplicate values.
2. Map can have single null key at most and any number of null values.
3. Set Map also doesn’t stores the elements in an order, however few of its classes does the same.
4. Classes in Maps HashMap, TreeMap, WeakHashMap, LinkedHashMap, IdentityHashMap etc.

## Q. What is the difference between HashSet and HashMap?

**HashSet**:-

1. HashSet class implements the Set interface
2. In HashSet, we store objects(elements or values) e.g. If we have a HashSet of string elements then it could depict a set of HashSet elements: {“Hello”, “Hi”, “Bye”, “Run”}
3. HashSet does not allow duplicate elements that mean you can not store duplicate values in HashSet.
4. HashSet permits to have a single null value.
5. HashSet is not synchronized which means they are not suitable for thread-safe operations until unless synchronized explicitly.


**HashMap**:-

1. HashMap class implements the Map interface
2. HashMap is used for storing key & value pairs. In short, it maintains the mapping of key & value (The HashMap class is roughly equivalent to Hashtable, except that it is unsynchronized and permits nulls.) This is how you could represent HashMap elements if it has integer key and value of String type: e.g. {1->”Hello”, 2->”Hi”, 3->”Bye”, 4->”Run”}
3. HashMap does not allow duplicate keys however it allows having duplicate values.
4. HashMap permits single null key and any number of null values.
5. HashMap is not synchronized which means they are not suitable for thread-safe operations until unless synchronized explicitly.

## Q. What is the difference between HashMap and TreeMap?
Java **HashMap** and **TreeMap** both are the classes of the Java Collections framework. Java Map implementation usually acts as a bucketed hash table. When buckets get too large, they get transformed into nodes of **TreeNodes**, each structured similarly to those in java.util.TreeMap.

|HashMap	                       |TreeMap                           |
|----------------------------------|----------------------------------|
|Java HashMap is a hashtable based implementation of Map interface.|Java TreeMap is a Tree structure-based implementation of Map interface.|
|HashMap implements Map, Cloneable, and Serializable interface.|TreeMap implements NavigableMap, Cloneable, and Serializable interface.|
|HashMap allows a **single** null key and multiple null values.|TreeMap does not allow **null** keys but can have multiple null values.|
|HashMap allows heterogeneous elements because it does not perform sorting on keys.|TreeMap allows homogeneous values as a key because of sorting.|
|HashMap is **faster** than TreeMap because it provides constant-time performance that is O(1) for the basic operations like get() and put().|TreeMap is **slow** in comparison to HashMap because it provides the performance of O(log(n)) for most operations like add(), remove() and contains().|
|The HashMap class uses the **hash table**.	|TreeMap internally uses a **Red-Black** tree, which is a self-balancing Binary Search Tree.|
|It uses **equals()** method of the Object class to compare keys. The equals() method of Map class overrides it.|It uses the **compareTo()** method to compare keys.|
|HashMap class contains only basic functions like get(), put(), KeySet(), etc. .|TreeMap class is rich in functionality, because it contains functions like: tailMap(), firstKey(), lastKey(), pollFirstEntry(), pollLastEntry().|
|Order of elements	HashMap does not maintain any order.|The elements are sorted in natural order (ascending).|
|The HashMap should be used when we do not require key-value pair in sorted order.|	The TreeMap should be used when we require key-value pair in sorted (ascending) order.|



## Q. What is the difference between HashMap and ConcurrentHashMap?
 	
|HashMap	                   |ConcurrentHashMap                                     |
|------------------------------|------------------------------------------------------|
|HashMap is not synchronized.  |ConcurrentHashMap is synchronized.|
|HashMap is not thread safe.   |ConcurrentHashMap is thread safe.|
|HashMap iterator is fail-fast and ArrayList throws ConcurrentModificationException if concurrent modification happens during iteration. |ConcurrentHashMap is fail-safe and it will never throw ConcurrentModificationException during iteration.|
|HashMap allows key and value to be null.|ConcurrentHashMap does not allow null key/value. It will throw NullPointerException.|
|HashMap is faster.     	   |ConcurrentHashMap is slower than HashMap.|


## Q. What is difference between arrayList and linkedList?

ArrayList and LinkedList both implements List interface and maintains insertion order. Both are non synchronized classes.

|ArrayList	                                                          |LinkedList                                         |
|--------------------------------------------------------------------|---------------------------------------------------
| ArrayList internally uses a dynamic array to store the elements.  |	LinkedList internally uses a doubly linked list to                                                                           store the elements. |
| Manipulation with ArrayList is slow because it internally uses an array. If any element is removed from the array, all the bits are shifted in memory.|Manipulation with LinkedList is faster than ArrayList because it uses a doubly linked list, so no bit shifting is required in memory.|
| An ArrayList class can act as a list only because it implements List only.|	LinkedList class can act as a list and queue |both because it implements List and Deque interfaces.|
| ArrayList is better for storing and accessing data. 	          |LinkedList is better for manipulating data.|


## Q. What is Comparable and Comparator Interface in java?

Comparable and Comparator both are interfaces and can be used to sort collection elements.

|Comparable	                |Comparator                                                                                |
|---------------------------|------------------------------------------------------------------------------------------|
|1) Comparable provides a single sorting sequence. In other words, we can sort the collection on the basis of a single element such as id, name, and price. |The Comparator provides multiple sorting sequences. In other words, we can sort the collection on the basis of multiple elements such as id, name, and price etc.|
|2) Comparable affects the original class, i.e., the actual class is modified.|Comparator doesn't affect the original class, i.e., the actual class is not modified.|
|3) Comparable provides compareTo() method to sort elements. | Comparator provides compare() method to sort elements.
|4) Comparable is present in java.lang package.|A Comparator is present in the java.util package.|
5) We can sort the list elements of Comparable type by Collections.sort(List) method.|We can sort the list elements of Comparator type by Collections.sort(List, Comparator) method.|

## Q. What is difference between HashSet and LinkedHashSet?
A HashSet is unordered and unsorted Set. LinkedHashSet is the ordered version of HashSet. The only difference between HashSet and LinkedHashSet is that LinkedHashSet maintains the **insertion order**. When we iterate through a HashSet, the order is unpredictable while it is predictable in case of LinkedHashSet. The reason why LinkedHashSet maintains insertion order is because the underlying data structure is a doubly-linked list.

## Q. What is the difference between HashTable and HashMap?
|HashMap	                                           |Hashtable                                               |
|------------------------------------------------------|--------------------------------------------------------|
|HashMap is **non synchronized**. It is not-thread safe and can't be shared between many threads without proper synchronization code. |	Hashtable is **synchronized**. It is thread-safe and can be shared with many threads.|
|HashMap allows one null key and multiple null values. |Hashtable doesn't allow any null key or value.|
|HashMap is a new class introduced in JDK 1.2. |Hashtable is a legacy class.|
|HashMap is fast.	                           |Hashtable is slow.|
|We can make the HashMap as synchronized by calling this code
 Map m = Collections.synchronizedMap(hashMap); | Hashtable is internally synchronized and can't be unsynchronized.|
|HashMap is traversed by Iterator.             |Hashtable is traversed by Enumerator and Iterator.|
|Iterator in HashMap is fail-fast.             |Enumerator in Hashtable is not fail-fast.|
|HashMap inherits AbstractMap class.           |	Hashtable inherits Dictionary class.|


## Q. What are the differences between ArrayList and Vector?
|ArrayList	                    |Vector                               |
|-------------------------------|-------------------------------------|
|ArrayList is **not synchronized**. |Vector is **synchronized**.              |
|ArrayList **increments 50%** of current array size if the number of elements exceeds from its capacity.|	Vector **increments 100%** means doubles the array size if the total number of elements exceeds than its capacity. |
|ArrayList is not a legacy class. It is introduced in JDK 1.2. |	Vector is a legacy class.|
|ArrayList is **fast** because it is non-synchronized. | Vector is **slow** because it is synchronized, i.e., in a multithreading environment, it holds the other threads in runnable or non-runnable state until current thread releases the lock of the object.|
|ArrayList uses the **Iterator** interface to traverse the elements. |A Vector can use the **Iterator** interface or **Enumeration** interface to traverse the elements.|
