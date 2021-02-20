## NOTES From Oracle Java Tutorial
![The Java Tutorials Lession: Interfaces](https://docs.oracle.com/javase/tutorial/collections/interfaces/index.html)

The core collection interfaces encapsulate different types of collections.  These interfaces allow collections to be manipulated independently of the details of their representation.  Core collection interfaces are the foundation of the Java Collections Framework.  The core collection interfaces form a hierarchy.
- Collection
    - SET... LIST... QUEUE... DEQUE
        - SORTEDSET

- Map
    - SORTEDMAP

# Set
A set is a special kind of COLLECTION, a SORTEDSET is a special kind of **set**. 

**NOTE - The hierarchy consists of two distinct trees - a Map is not a true Collection.

**NOTE - All the core collection interfaces are generic.  This is an example of a declaration of the Collection interface.

public interface Collection<E>

The <E> syntax tells you that the interface is generic.  When you declare a COLLECTION instance you can and should specify the type of object contained in the collection.  Specifying the type allows the compiler to verify (at compile-time) that the type of object you put into the collection is correct, thus reducing errors at runtime.

The following list describes the core collection interfaces:
- COLLECTION- the root of the collection hierarchy.  A collection represents a group of objects known as its elements.  The COLLECTION interface is the least common denominator that all collections implement and is used to pass collections around and to manipulate them when maximum genrality is desired.  Some types of collections allow duplicate elements, and others do not.  Some are ordered and others are unordered.
- SET- a collection that cannot contain duplicate elements.  This interface models the mathematical set abstraction and is used to represent sets, such as the cards comprising a poker hand, the courses making up a student's schedule, or the processes running on a machine.
- LIST- an ordered collection (sometimes called a sequence).  Lists can contain duplicate elements.  The user of a List generally has precise control over where in the list each element is inserted and can access elements by their integer index (position).  If you've used Vector, you're familiar with the general flavor of List.
- QUEUE- a collection used to hold multiple elements prior to processing. Besides basic COLLECTION operations, a Queue provies additional insertion, extraction, and inspection operations.

Queues typically, but do not necessarily, order elements in a FIFO (first, in, first-out) manner.  Among the exceptions ar epriority queues, which order elements according to a supplied comparator or the elements' natural ordering.  Whatever the ordering used, the head of the queue is the element that would be removed by a call to *remove* or *poll*. In a FIFO queue, all new elements are inserted at the tail of the queue.  Other kinds of queues may use different placement rules.  Every Queue implementation must specify its ordering properties. 

- DEQUE- a collection used to hold multiple elements prior to processing.  Besides basic COLLECTION operations, Deque provides additional insertion, extraction, and inspection operations.

Deques ccan be used both as FIFO and LIFO (last, in, first-out).  In a deque all new elements can be inserted, retrieved and removed at both ends.

- MAP- an object that maps key to values (x, y).  A Map cannot contain duplicate keys; each key can map to at most one value. If you've used Hashtable, you're already familiar with the basics of Map.

## SortedSet
SortedSet is a set that maintains its elements in ascending order.  Several additional operations are provided to take advantage of the ordering.  Sorted sets are used for naturally ordered sets, such as word list and membership rolls.  

## SortedMap
SortedMap is a map that maintains its mappings in ascending key order.  This is the Map analog of SortedSet.  Sorted maps are used for natually ordered collections of key/value pairs, such as dictionaries and telephone directories.

