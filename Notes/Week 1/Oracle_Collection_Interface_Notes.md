A COLLECTION represents a group of objects known as ite elements.  The COLLECTION interface is used to pass around collections of objects where maximum generality is desired.  For example, by convention all general-purpose collection implementations have a constructor that takes a COLLECTION argument.  This constructor, known as a *conversion constructor*, initializes the new collection to contain all of the elements in the specified collection, whatever the given collection's subinterface or implementation type.  In other words, it allows you to convert the collection's type.

- For example, you have a Collection<String> c, which may be a List, a Set, or another kind of Collection.  This idiom creates a new ArrayList (an implementation of the List interface), initially containing all the elements in c.

`List<String> list = new ArrayList<String>(c);`

The Collection interface contains methods that perform basic operations, such as int size(), boolean isEmpty(), boolean contains (Object element), boolean add (E element), boolean remove (Object element), and Iterator<E> iterator().

It also contains methods that operate on entire collections, such as boolean containsAll (Collection<?> c), boolean addAll (Collections <? extends E> c), boolean removeAll (Collection<?> c), boolean retainAll (Collection<?> c), and void clear().

Additional methods for array operations: such as Object[] toArray() and <T>T[] toArray(T[] a) exist as well.