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