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