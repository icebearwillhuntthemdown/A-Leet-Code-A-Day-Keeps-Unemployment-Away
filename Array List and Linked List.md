# Array List and Linked List

## Array List
```java
List<Object> arrayListName = new ArrayList<>();
```
Array list can be taken as a resizable array that holds objects. Unlike array, array list is a **class** itself hence we instantiate one with **new** keyword and a constructor. Another difference between array and array list is, array list can't hold a primitive type and you need to use an wrapper class(autoboxing) instead of the primitive type. 

## Linked List
```java
List<Object> linkedListName = new LinkedList<>();
```
Just like array list, linked list also is a class and holds objects. But in linked list, each element has **a value and a reference** to the next element. When you add or remove an element from an array list it automatically shifts the subsequent elements, which can lead to massive resource usage. Unlike array list, there's no need to shift the elements in linked list, as all that needs to be done is just **changing the reference to**. If you add an element in linked list at the index of 3, the reference of the element of index 2 is being changed to the new element. If you remove an element from a linked list at index 4, the element at index 3 now points to what used be element of index 5. Garbage collector will automatically remove the elements without any reference to them. 

### Iteration of Linked List
Even though linked list also has indices, it's not efficient to interate by index.
```java
List<String> userNames = new LinkedList<>();
Iterator<Object> i = userNames.iterator();

while(i.hasNext()){
  System.out.println(i.next());
}
```
##### Iteration interface Methods
* boolean hasNext() : returns true if the iteration has more elements.
* next() : returns the next element in the iteration.

#### List Interface Methods
Both array list and linked list implement List interface, hence share methods below.
* int size() : Returns the number of elements in the list.
* boolean isEmpty() : Returns true if the list is empty and false otherwise.
* boolean contains(Object o) : Returns true if there's the element in the list and false otherwise.
* get(int index) : Returns the element at the position
* set(int index, element) : Replaces the element at the specified position with the element taken.
* boolean add(element) : Appends the specified element to the end of the list and returns true.
* add(int index, element) : Inserts the specified element at the specified position and shifts the element currently at the position and any subsequent elements to the right
* boolean remove(Object o) : Removes the element with the lowest index and returns true if the list contained the specified element.
* remove(int index) : Removes the element at the specified position and shifts any subsequent elements to the left. Returns the removed element.
* int indexOf(Object o) : Returns the lowest index of the specified element, or -1 is this list doens't contain the element.
* boolean addAll(Collection c) : Copies all the elements of the collection and appends them at the end of the list. Returns true if the list's been changed.
  * ArrayList, LinkedList의 경우 생성자의 파라미터로 다른 컬렉션을 복사할 수도 있다.  
  `List<String> newArrayList = new ArrayList<String>(originalArrayList);`
* boolean addAll(int index, Collection c) : Do the same as above but at the specified position.
* boolean removeAll(Collection c) : Removes all the elements from the list that are contained in the specified collection. Returns true if the list's been changed.
* boolean retainAll(Collection c) : Retains only the elements that are in the specified collection and returns true if the list's been changed.
