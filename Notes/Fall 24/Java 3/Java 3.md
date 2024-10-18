Data Structures et al

Just fucking go to all the labs and classes dumbass.
All labs are grade *after* the class and are all graded using **Unit Testing!** You need to make sure you actually submit your work!

**Test Driven Design** -> writing code by writing the test first, thus having your output in mind.

Labs:
4 Programs:
- 2-D arrays (Lab 1 & 2)
- Stacks / Queues (Lab 4 - 6)
- Trees (Lab 7 - 9)
- Hashing (Lab 10 - 12)

There are *prelabs* for all 12 labs. They will help us not have to spend 12 hours for each lab.

Test:
Each test is 20% of the grade. 
Final exam is optional. :D
A: 92-100
A- : 90-91
B+ : 86 - 89

Prelabs go away at 4 p Friday and the new prelab open 4:30 p the same day.

Declaring an array of class objects:
```java
import java.util.ArrayList;

public class ClassName {
	ArrayList<ClassName> list = new ArrayList<>();
	
}
```

Remember:
```java
ArrayList.add(value); // add a value to the end of the list
ArrayList.add(int index, value); // add value to a certain index
ArrayList.set(0, value); // overwrite an index with a varible
ArrayList.remove(int index); // removes a value at a given index
ArrayList.size(); // returns the logical lenght of the ArrayList
ArrayList.get(int index); // get the value at a given index
```

For Each loop:

```java
for (ClassName object : list) {
	// Do your code here
}
```

# Inheritance, Polymorphism, Abstract Classes, and Interfaces

The four pillars of object oriented programming are:
- Encapsulation
- Polymorphism
- Abstract
- Abstract Classes

**Aggregation** is a "*has a*" relationship and **Inheritance** is a "*is a*" relationship.

You can only ever inherit for one class, but you can implement as many interfaces as you like.

```java
public class BoardGame implements Game {...} // implimented
public class Monopoly extends BoardGame {...} // inherited
```

Remember: *all object inherit from the $Object$ class.*

$Object$ has two methods:
- toString
	- Called when you try to print an object
- equals
	- used in equality checks (think if statements), by default checks that if two objects have the same memory reference. The $String$ method overrides this. 


# Chapter 12: Collections & Stacks
**Collection:** data elements organized in a certain way to allow for accessing and managing the elements

Collection Types:
- Linear (in sequence)
- Nonlinear 

Collection Organization
- **Order** to the way elements are added
- **Inherent relationship** among elements

Collections are **Abstractions**
- **Interface** defines operations

(ADT) **Abstract Data Types** - the idea that we are only going to implement these methods because the interface tells us to.

**Collection Types**
- Sets
- lists
- stacks
- queues
- priority queues

**Generics**
You create the data structure *once* then you have many applications for the data structure.

Reference variable = Object type
The reference variable must be:
- The same class as the Object
- A superclass of the Object.

**Generic Types** define the data type when instantiated

Example:
```java
class Box <T> {
	// T is a placeholder for the data type.
	...
}
```

## Stacks
Linear collection of elements. Remember **LIFO**
**L** - Last In
**I** - In
**F** - First
**O** - Out

Common operations with LIFO are:
- Push - add an element
- Pop - remove an element
- Peek - examine top element
- isEmpty - true or false if stack is empty
- Size - number of elements

Example of a stack is the Fibonacci Sequence:

Pseudocode:
1. Push 1 and 1 on the stack
 2. pop the first element
 3. peek second element
 4. push the first element back on
 5. push the sum of the first and second element.
 6. repeat 2-5.

If the problem you are trying to solve requires movement other than the top of a stack, you need to choose a different data structure.

## Infix, Postfix, and Prefix

Infix: $(4+8) / (12 * 2)$  this is what we are used to, it follows PEDMAS
Postfix: $4\ 8+12\ 2\ *\ /$ 
Prefix: $/\ +\ 4\ 8\ 12\ 2$ 

All equations mean the same thing.

Post fix can be explained with a stack.
When you have a number you keep moving on. When we encounter the plus, we look back on the previous two numbers. Find a video on this if you're too confused future Joey, I can't write all this down at the moment.

Pseudocode for Postfix:
1. If `char` is a number, push onto stack
2. If  `char` is an operator, 
	1. `n2` is what we pop
	2. `n1` is the next pop
	3. push (`n1` operator `n2`)

Rather simple actually.

With post fix it's rather easy to check if the expression is invalid. For example, the stack size at the end should always be one. When using operators, there should always be two items in the stack.

*Ordered List*
An ordered list is when you add an element to a list and it's in some sort of order.

An Unordered list is the exact opposite. The order doesn't matter.

---
**Queues**
Queues are FIFO. They have most of the same commands as Stacks and Linked lists. The main two new methods are `.enqueue()` and `.dequeue()`. 

A good example of queue usage is *Radix Sort*:
- Create an array of 10 queues, one for each digit (0-9)
- Start with the least significant figure and add it to the queue of the corresponding number
- Dequeue from the top to the bottom ($q0,\ q1,\ q3,\ ...,\ q9$)
- Repeat with the next least significant figure adding leading $0$s as needed.
- Repeat until out of significant figure
**Josephus Problem**
Gonna need to look this up after class. I didn't catch it.

**Serializable Interface**
Serializable Interfaces have *No methods*. This tells the Java compiler that object can be serialized.

It can be explained with the fence-post analogy. You can think of the rails of of fence as holding the actual information between two posts.

The *Comparable Interface* requires the `compareTo()` method to be implemented.

E.g. `obj0.compareTo(obj1);`
`result = obj0 - obj1`
- If `result < 0`, `obj0 < obj1`
- If `result == 0`, `obj0 == obj1`
- If `result > 0`, `obj0 > obj1`

In Java, serializable interfaces must work with classes that implement the *Comparable Interface*.

**Sorted List Creation**
This list type needs these capabilities in the `add()` method.
1. Add first node onto an empty list
	1. is the list empty?
2. Add a value greater than the tail
	1. is the new node $<$ head?    
3. Add a value less than the head
	1. is the new node $\ge$ tail? 
4. Add a value in the middle (do this last)
	1. to get the middle element traverse the list until `obj1` is $\le$ (or $>$) to `obj0`
	2. Note that you need to use `previous` and `current` values

----
**Iterators**

The iterators live on  the fence posts. It can only move down the fence post. As long as a rail exists, `Iterator.hasNext()` will be true.

You cannot modify a list or data structure while an iterator is being used.

Iterable interface allows us to use a for-each loop.

Thus the iterable is the only reason why we are able to use for-each loops.
 
 ------
**Recursion**

A recursive method is one that calls itself. Like a loop, a recursive method must have some way to control the number of times it repeats. The **depth of recursion** is the number of times the method calls itself (excluding the first call from a driver or other class).

The advantage of recursive is that it's easier to read. However, they are less efficient memory-wise. Thus they **allocate more memory** and **must store the address of where the control returns** after the method terminates.

Recursion takes a **larger problem** and simplifies it into a **smaller problem**. 

Recursion works like this:
- **Base case**
	- Small problem that can be solved directly
	- Method solves the problem and returns
- **Recursive case**:
	- Repeats the base case until the problem is done.
	- Is the inverse of the Base Case

Direct and Indirect Recursion

Direct:
$$A \rightarrow A$$

Indirect:
$$A \rightarrow B \rightarrow C \rightarrow A$$
**Post-Recursion** is when we do the *work* before the *recursive call*
**Pre-Recursion** is when we do the *recursive call* before the *work is done*.

---
# Trees
A *tree* is a non-linear data structure in which elements are organized into a *hierarchy*.

Terminology:
- A *tree* is composed of *nodes* (elements)
- *Edges* connect nodes together
- The *root* is the only node at the top *level* (0)
- *Children* are a level below their *parents*
- Each node (except the root) has exactly ONE parent, but can have multiple children
- Nodes that have the same parent are called siblings
- A node with no children is a *leaf*
- A node that is not the root, and has at least one child is an internal node
- The root acts as an "entry point" into the tree. Follow a *path* from the root to a node.
- The *ancestors* of a node are the nodes on the path from the root to the node
- A *sub-tree* is a tree structure that includes the root of the sub-tree and all of its descendants
- The *height* of a tree is the length of the longest path. Found by counting the edges.
- The *Order* of the tree is that maximum number of children for a node
	- *General Tree* is a tree with no limit of children
	- *n-Array Tree* is a tree with only n children allowed
- A *Balanced* tree is when all leaves are at the same level or within 1 level
- A *Complete* tree is a balanced tree that has all leaves are to the left.
- A *Full* tree has all leaves are at the same level.
	- Every node has exactly **n children** or is a **leaf**.

Hierarchy of **Balanced, Complete**, and **Full**: $Balanced\ \rightarrow \ Complete\ \rightarrow\ Full$


![[Pasted image 20241014141906.png]]
![[Pasted image 20241014141947.png]]
![[Pasted image 20241014142337.png]]

**Tree Traversal**

*In-Order*: Left Child $\rightarrow$ Visit $\rightarrow$ Right Child
*Pre-Order*: Visit $\rightarrow$ Left Child $\rightarrow$ Right Child
*Post-Order*: Left Child $\rightarrow$ Right Child $\rightarrow$ Visit
*Level-Order* visit all the nodes on that level. Aka *Breadth First*

**Huffman Coding**
The **Huffman Coding** algorithm is a compression algorithm that uses a *priority queue*.

*Priority Queues follows **two rules***:
- Initially order with the **highest priority** first in the queue.
- Nodes with the **same priority** are ordered by FIFO.
![[Pasted image 20241016141340.png]]
![[Pasted image 20241016141359.png]]
![[Pasted image 20241016141529.png]]

Notice that one you build the tree, all the letters are leaves.

By taking the encoded text, you traverse from the root until you hit a leaf, then you print the leaf and start over.




