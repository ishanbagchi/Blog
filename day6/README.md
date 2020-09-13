# Complete guide to Linked Lists in JavaScript

A **Linked List** is a sequential structure that consists of a sequence of items in linear order which are linked to each other.

![linked list image](https://ishanbagchi.github.io/Ishan-Tech-Blog/day4/images/linked-list.png)

```javascript
class Node { 
	constructor(element) 
	{ 
		this.element = element; 
		this.next = null
	} 
} 
```

Here, a node is been created, using a constructor, which stores two parameters:
> * **element** : value
> * **next** : location to the next node

> The location to the next node is stored as a null value in the beginning.

### Now let us implement in the `LinkedList` class 

```javascript
// LinkedList class 
class LinkedList { 
	constructor() 
	{ 
		this.head = null; 
		this.size = 0; 
	} 

	// Main Functions
	// add(element) 
	// insertAt(element, location) 
	// removeFrom(location) 
	// removeElement(element) 

	// Helper Functions 
    // indexOf(element)
	// isEmpty()
	// sizeOfList() 
	// printList()
} 
```

The above program displays the _constructor_ and _the list of methods to be implemented_. The class comprises of two property:
> * **head** : stores the first node of the list
> * **size** : stores the size of the list

## Main Functions

> ### add(element)

```javascript
// adds an element at the end of list 
add(element) { 
	// creates a new node 
	var node = new Node(element); 

	// to store current node 
	var current; 

	// if list is Empty add the element and make it head 
	if (this.head == null) 
		this.head = node; 
	else { 
		current = this.head; 

		// iterate to the end of the list 
		while (current.next) { 
			current = current.next; 
		} 

		// add node 
		current.next = node; 
	} 
	this.size++; 
} 
```
Our approach here is first _if the list is empty, we are adding the element in the begining_, else _we are continuously pushing the element in the next node and adding the element in the end_. `current` is used to iterate through the list after every iteration we update it to be the `next` of the current node. If next is null(the last element of a list contains null in the next) then we add the element to the list.

> ### insertAt(element, index)

```javascript
// insert element at the position 'index' of the list 
insertAt(element, index) { 
	if (index > 0 && index > this.size) 
		return false; 
	else { 
		// creates a new node 
		var node = new Node(element); 
		var current, previous; 

		current = this.head; 

		// add the element to the first index 
		if (index == 0) { 
			node.next = this.head; 
			this.head = node; 
		} else { 
			current = this.head; 
			var it = 0; 

			// iterate over the list to find the position to insert 
			while (it < index) { 
				it++; 
				previous = current; 
				current = current.next; 
			} 

			// adding an element 
			node.next = current; 
			previous.next = node; 
		} 
		this.size++; 
	} 
} 
```

Our approach here is _if the index is zero we add an element at the front of the list and make it head_, _if the index is the last position of the list we append the element at the end of the list_ else, _if the index is between 0 or size – 1 we iterate over to the index and add an element at that index_ 
> previous holds the previous of current node

> ### removeFrom(index)

```javascript
// removes an element from the 'index'th location 
removeFrom(index) { 
	if (index > 0 && index > this.size) 
		return -1; 
	else { 
		var current, previous, it = 0; 
		current = this.head; 
		previous = current; 

		// deleting first element 
		if (index == 0) { 
			this.head = current.next; 
		} else { 
			// iterate over the list to the position to remove an element 
			while (it < index) { 
				it++; 
				previous = current; 
				current = current.next; 
			} 

			// remove the element 
			previous.next = current.next; 
		} 
		this.size--; 

		// return the remove element 
		return current.element; 
	} 
} 
```

Our approach here is _if the index is 0 then we remove the head and make the next node head of the list_, _if the index is size – 1 then we remove the last element from the list and make previous the last element_, lastly _if it is in between 0 to size – 1 we remove the element by using previous and current node_. 

> ### removeElement(element)

```javascript
// removes a given element from the list 
removeElement(element) { 
	var current = this.head; 
	var previous = null; 

	// iterate over the list 
	while (current != null) { 
		// comparing element with current element 
        // if found 
            // then remove the element 
            // and return true 
		if (current.element == = element) { 
			if (previous == null) { 
				this.head = current.next; 
			} else { 
				previous.next = current.next; 
			} 
			this.size--; 
			return current.element; 
		} 
		previous = current; 
		current = current.next; 
	} 
	return -1; 
} 
```

This function is nearly the same as _removeFrom(index)_, just here, we are searching the element and removing it.

## Helper functions

> ### indexOf(element)

```javascript
// finds the index of element 
indexOf(element) { 
	var count = 0; 
	var current = this.head; 

	// iterae over the list 
	while (current != null) { 
		// compare each element of the list with given element 
		if (current.element == element) 
			return count; 
		count++; 
		current = current.next; 
	} 

	// not found 
	return -1; 
} 
```

In this method, we iterate over the list to find the index of an element. If it is not present in the list it returns -1 instead.

> ### isEmpty()

```javascript
// checks the list for empty 
isEmpty() { 
	return this.size == 0; 
} 
```

In this method we check for the _size_ property of the _LinkedList_ class, and if its **zero** then the list is empty.

> ### sizeOfList()

```javascript
// gives the size of the list 
sizeOfList() { 
	console.log(this.size); 
} 
```

Simply displays the _size_ property of the _LinkedList_ class.

> ### printList()

```javascript
// prints the list items 
printList() { 
	var current = this.head; 
	var str = ""; 
	while (current) { 
		str += current.element + " "; 
		curr = current.next; 
	} 
	console.log(str); 
} 
```

In this method, we iterate over the entire list and concatenate the elements of each node and print it.

## Implementation

Now we will use different functions from the above.

```javascript
// creating an object for the Linkedlist class 
var list = new LinkedList(); 

// testing isEmpty on an empty list
console.log(list.isEmpty()); 
// returns true 

// adding element to the list 
list.add(10); 

list.printList(); 
// prints 10 

console.log(list.sizeOfList()); 
// returns 1 

// adding more elements to the list 
list.add(20); 
list.add(30); 
list.add(40); 
list.add(50); 

list.printList(); 
// returns 10 20 30 40 50 

// prints 50 from the list 
list.removeElement(50); 

list.printList(); 
// prints 10 20 30 40 

console.log("Index of 40 " + list.indexOf(40)); 
// returns 3 

list.insertAt(60, 2); 
// insert 60 at second position 

list.printList(); 
// list contains 10 20 60 30 40 

console.log("Is List Empty ? " + list.isEmpty()); 
// returns false

console.log(list.removeFrom(3)); 
// remove 3rd element from the list 

list.printList(); 
// prints 10 20 60 40 
```

## Acknowledgement
+ [GeekForGeeks](https://www.geeksforgeeks.org/)

> If I have made any mistake in the article please comment on it.  