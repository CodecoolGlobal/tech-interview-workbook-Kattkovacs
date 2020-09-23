# OOP questions

## Software design

### Error handling

#### 1. What does 'fail fast' mean in terms of exception handling? Why is it a good practice?

In systems design, a fail-fast system is one which immediately reports at its interface any condition that is likely 
to indicate a failure. Fail-fast systems are usually designed to stop normal operation rather than attempt to continue 
a possibly flawed process. Such designs often check the system's state at several points in an operation, 
so any failures can be detected early. The responsibility of a fail-fast module is detecting errors, 
then letting the next-highest level of the system handle them.

## Computer Science

### Data structures

#### 2. How to find the middle element of singly linked list in O(n)?

Big O notation is a mathematical notation that describes the limiting behavior of a function when the argument 
tends towards a particular value or infinity. / Big O notation, indicating the order of growth of some quantity 
as a function of n or the limiting behavior of a function.
A/ Traverse the whole linked list and count the no. of nodes. Now traverse the list again till count/2
B/ Traverse linked list using two pointers. Move one pointer by one and other pointer by two. When the fast pointer 
reaches end slow pointer will reach middle of the linked list.
C/ Initialize mid element as head and initialize a counter as 0. Traverse the list from head, while traversing 
increment the counter and change mid to mid->next whenever the counter is odd. So the mid will move only half 
of the total length of the list.

#### 3. Given an array of integers going from 1 to 100 (both inclusive) there is a duplicated entry. How to find it?

Brute Force
The brute force solution is to implement two nested loops.
Count Iterations
Another solution is to have a data structure to count the number of iterations of each integer. 
This solution could be implemented either with an array or a hash table.
Sorted Array
If we apply the simplification technique, we could try to find a solution with a sorted array. 
In this case, we would just have to compare each element with its right neighbor.
Sum of the Elements
A direction we may think about is to sum the elements of the array and to compare it with 1 + 2 + … + n. 
It's working solely in the case where we have one duplicate.

#### 4. What is a linked list? How to find if a linked list has a loop?

The LinkedList data structure is a linear data structure where the elements are not stored in contiguous locations 
and every element is a separate object with a data part and address part. The elements are linked using pointers 
and addresses. Each element is known as a node. Due to the dynamicity and ease of insertions and deletions, 
they are preferred over the arrays. It also has few disadvantages like the nodes cannot be accessed directly 
instead we need to start from the head and follow through the link to reach to a node we wish to access. 
Linked List is a part of the Collection framework present in java.util package.  find if a linked list has a loop:
Hashing - HashSet s = new HashSet(); Traverse the list one by one and keep putting the node addresses in a Hash Table. 
At any point, if NULL is reached then return false and if next of current node points to any of the previously stored 
nodes in Hash then return true.
Modifying the linked list data-structure Have a visited flag with each node. 
Traverse the linked list and keep marking visited nodes. If you see a visited node again then there is a loop. 
This solution works in O(n) but requires additional information with each node. A variation of this solution that 
doesn’t require modification to basic data structure can be implemented using a hash, just store the addresses of 
visited nodes in a hash and if you see an address that already exists in hash then there is a loop. 
3: Fastest: 
Floyd’s Cycle-Finding Algorithm Traverse linked list using two pointers. 
Move one pointer(slow_p) by one and another pointer(fast_p) by two. 
If these pointers meet at the same node then there is a loop. 
If pointers do not meet then linked list doesn’t have a loop.

#### 5. What is the Big O time complexity of the common operations in an ArrayList, LinkedList, HashMap? And of a bubble sort, quicksort, finding items in a Binary Search tree?

Big O Notation is a mathematical function used in computer science to describe how complex an algorithm is — 
or more specifically, the execution time required by an algorithm. In software engineering, 
it’s used to compare the efficiency of different approaches to a problem. With Big O Notation, 
you express the runtime in terms of how quickly it grows relative to the input, as the input gets arbitrarily large. 
Essentially, it’s a way to draw insights into how scalable an algorithm is. 
It doesn’t tell you how fast or how slow an algorithm will go, but instead about how it changes with respect to 
its input size. Big O time complexity = Worst Case Time Complexity [ Big-O ] Common varieties of Big O Notation O(1) 
- Constant time complexity: This translates to a constant runtime, meaning, regardless of the size of the input, 
the algorithm will have the same runtime. O(log n) - Logarithmic time complexity: O(log n) means that time goes 
up linearly, while the n goes up exponentially. So if it takes 1 second to compute 10 elements, it will take 
2 seconds to compute 100 elements and so on. It is O(log n) when we use divide and conquer algorithms 
e.g binary search. O(n) - Linear time complexity: O(n) describes an algorithm whose performance will grow linearly 
and in direct proportion to the size of the input data set. ArrayList: add(), get() - O(1), 
We have to iterate the entire array: 
remove(), indexOf(), contains() - O(n) 
LinkedList (linear data structure): add() - O(1), get() - O(n), remove() - O(1), contains() - O(n) 
HashMap: insert and retrieve a value is O(1) on average (faster than lists) 
Bubble sort: O(n2) Quicksort: O(log(n)) 
Finding items in a Binary Search tree: O(log n) 
(There’s a fine cheatsheet about all type of complexity of Data Structures and algorithms.)

#### 6. How does HashMap work?

Hashing: It is the process of converting an object into an integer value. 
The integer value helps in indexing and faster searches. HashMap is a part of the Java collection framework. 
It uses a technique called Hashing. It implements the map interface. 
It stores the data in the pair of Key and Value. 
HashMap contains an array of the nodes, and the node is represented as a class. It uses an array and 
LinkedList data structure internally for storing Key and Value. Map stores the data using hashcode() and equals() 
method from key. HashMap<String, Integer> map = new HashMap<>(); map.put("Aman", 19); 
hashCode(Key): This is the method of the object class. It returns the memory reference of the object in integer form.

#### 7. Why is it important for keys in a map to have an immutable type? (Consider String for example.)

There is an Employee class (mutable) which we want to use as a key in Hashmap. 
With this mutable class we create an instance of Employee and put it in a hashmap: 
```java
Employee key = new Employee("name1", "id1"); 
hashmap.put(key, "some value"); 
```
Let's assume that it has generated some hashcode like 123456 for given name and id, and it has calculated 
the index as 1 basis on that & then stored the value at related location. 
Now we call the setter on name or id on object "key" and it's hashcode is changed, 
let's assume now it has hashcode as 234567 and index position as 4. for ex: 
```java
key.setName("other name");
```
If we try to search the map for this key, it may not find a value as it's 
hashcode is changed and hashmap has calculated different index position for this key. 
Now if we call the put() method on map with this key, it will store this object at different position and 
bucket in the hashmap. It may result in some memory leak as we still have the same employee object (key) as a key 
in map with the previous hashcode 123456.

### Other

#### 8. What is a garbage collector, in a nutshell?

In computer science, garbage collection (GC) is a form of automatic memory management. 
The garbage collector, or just collector, attempts to reclaim garbage, or memory occupied by objects that are 
no longer in use by the program. Garbage collection was invented by John McCarthy around 1959 to simplify 
manual memory management in Lisp.

## Programming paradigms

### Procedural

#### 9. What is casting? What is the difference between up vs downcasting?

Casting means picking an Object of one specific type and making it into another Object type. 
This process is called casting a variable. Like otherwise, it refers to the change of one data type to another. 
When you cast a particular variable, the data type of the variable itself will not get altered. Lets see with 
an example, in the following code, when we cast, num1 to a double; the variable num1 will not alter its data type 
from int to double. Alternatively, another new copy of num1 is built and its data type is turns as double. 
int num1=3, num2=4; double result = (double) num1 / num2; 
Upcasting is casting a subtype to a supertype, upward to the inheritance tree. 

Let’s see an example: 
Dog dog = new Dog(); Animal anim = (Animal) dog; anim.eat(); or Animal anim = new Dog(); 

Here, we cast the Dog type to the Animal type. 
Because Animal is the supertype of Dog, this casting is called upcasting. 
Note that the actual object type does not change because of casting. The Dog object is still a Dog object. 
Only the reference type gets changed.
Upcasting is always safe, as we treat a type to a more general one. In the above example, an Animal has all 
behaviors of a Dog. Generally, upcasting is not necessary. Downcasting is casting to a subtype, downward 
to the inheritance tree. Animal anim = new Cat(); Cat cat = (Cat) anim; Here, we cast the Animal type to the Cat type. 
As Cat is subclass of Animal, this casting is called downcasting. 
Downcasting can fail if the actual object type is not the target object type. 
Animal anim = new Cat(); Dog dog = (Dog) anim; 
This will throw a ClassCastException because the actual object type is Cat. 
And a Cat is not a Dog so we cannot cast it to a Dog. 
The Java language provides the instanceof (operator) keyword to check type of an object before casting. 
Use downcasting when we want to access specific behaviors of a subtype.

#### 10. Which order should we catch the exceptions? Why?

The order is whatever matches first, gets executed. 
If the first catch matches the exception, it executes, if it doesn't, the next one is tried and on and on until 
one is matched or none are. So, when catching exceptions you want to always catch the most specific first and 
then the most generic (as RuntimeException or Exception). It's also a compilation error to catch a generic exception 
first and then one of it's descendants later ( compilation error: first Exception, next RuntimeException).

### Object-oriented

#### 11. What is a class?

In object-oriented programming, a class is an extensible program-code-template for creating objects, 
providing initial values for state (member variables) and implementations of behavior (member functions or methods).
In many languages, the class name is used as the name for the class (the template itself), 
the name for the default constructor of the class (a subroutine that creates objects), 
and as the type of objects generated by instantiating the class.
When an object is created by a constructor of the class, the resulting object is called an instance of the class, 
and the member variables specific to the object are called instance variables, 
to contrast with the class variables shared across the class.

#### 12. What is an object?

In the class-based and object-oriented programming paradigms, object refers to a particular instance of a class, 
where the object can be a combination of variables, functions, and data structures. 
An object is an abstract data type with the addition of polymorphism and inheritance.

#### 13. What is a constructor?

In class-based object-oriented programming, a constructor is a special type of method of class called to create an object. 
It's name is same as the class name. It prepares the new object for use, often accepting arguments that 
the constructor uses to set required member variables. 
A constructor resembles an instance method, but it differs from a method in that it has no explicit return type, 
it is not implicitly inherited and it usually has different rules for scope modifiers. Constructors often have 
the same name as the declaring class. They have the task of initializing the object's data members and of establishing 
the invariant of the class, failing if the invariant is invalid. A properly written constructor leaves 
the resulting object in a valid state. Immutable objects must be initialized in a constructor. 
Most languages allow overloading the constructor in that there can be more than one constructor for a class, 
with differing parameters. 
In Java, constructors differ from other methods in that: 
Constructors never have an explicit return type, it'sname same as the class. 
Constructors cannot be directly invoked (the keyword “new” invokes them). 
Constructor can be overloaded with different parameters.
At Singleton, the constructor is private.
Constructors cannot be synchronized, final, abstract, native, or static. 
It should not contain modifiers Java constructors perform the following tasks in the following order:
-   1/ Call the default constructor of the superclass if no constructor is defined. 
-   2/ Initialize member variables to the specified values. 
-   3/ Executes the body of the constructor.
Abstact class has constructor.

#### 14. Do we require parameter for constructors?

There are 3 type of constructor in Java: 
-   Default: not seen in code, has no parameter, body is empty. If we don’t define a constructor in a class, 
then compiler creates default constructor (with no arguments) for the class. 
-   No-argument constructor: seen in code, has no parameter, body can be empty, or filled with code. 
-   Parameterized Constructor: A constructor that has parameters is known as parameterized constructor. 
If we want to initialize fields of the class with your own values, then use a parameterized constructor. 
Body is filled with code, parameters are used.

```java
class Geek { String name; int id;
Geek(String name, int id) { 
    this.name = name; 
    this.id = id; 
    } 
}
```

#### 15. What is an interface?

An interface is a contract between a class and the outside world. When a class implements an interface, 
it promises to provide the behavior published by that interface. In its most common form, an interface is a group 
of related methods with empty bodies. If your class claims to implement an interface, all methods defined by 
that interface must appear in its source code before the class will successfully compile.

#### 16. What are access modifiers?

Access level modifiers determine whether other classes can use a particular field or invoke a particular method. 
There are two levels of access control:
At the top level—public, or package-private (no explicit modifier).
At the member level—public, private, protected, or package-private (no explicit modifier). A class may be declared 
with the modifier public, in which case that class is visible to all classes everywhere. If a class has no modifier 
(the default, also known as package-private), it is visible only within its own package.
At the member level, you can also use the public modifier or no modifier (package-private) just as with top-level classes, 
and with the same meaning. For members, there are two additional access modifiers: private and protected. The private 
modifier specifies that the member can only be accessed in its own class. 
The protected modifier specifies that the member can only be accessed within its own package (as with package-private) 
and, in addition, by a subclass of its class in another package.

#### 17. What is data hiding?

Encapsulation is one of the four fundamental OOP concepts. The other three are inheritance, polymorphism, and abstraction. 
Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together 
as a single unit. In encapsulation, the variables of a class will be hidden from other classes, and can be accessed 
only through the methods of their current class. Therefore, it is also known as data hiding. 
To achieve encapsulation in Java:
Declare the variables of a class as private.
Provide public setter and getter methods to modify and view the variables values.

#### 18. Can a static method use non-static members?

In static method, the method can access only static data members and static methods of another class or same 
class but cannot access non-static methods and variables.

#### 19. What is the difference between hiding a static method and overriding an instance method?

Instance methods and class methods have this important difference in behavior, we use different terms - 
"overriding" for instance methods and "hiding" for class methods - to distinguish between the two cases. 
And when we say you can't override a static method, what that means is that even if you write code that looks 
like it's overriding a static method (like the first Foo and Bar at the top of this page) - it won't behave like 
an overridden method, because the compiler only uses the declared type of the reference. 
That's what we mean when we say a static method does not have run-time polymorphism.
When you override a method, a child method replaces the parent method in calls defined in both the parent and child. 
But when you hide a static method, the hidden method only replaces the parent methods in the class defined in the subclass.

The following table summarizes what happens when you define a method with the same signature as a method in a superclass:

|          |Superclass instance method|Super class static method|
|----------|:-------------:|------:|
| Subclass instance method|Overrides|Generates compile-time error|
| Sublcass static method|Generates compile-time error|Hides|

#### 20. Define the following terms: Instantiation, Attribute, Method

-  Instantiation: In object-oriented programming, an object is an instance of a class. Creating a new instance of 
that class is instantiation. 
-  Attribute: An attribute is another term for a field and for a variable. It’s typically a public field that can be 
accessed directly. Let’s see a particular case of Array, the array is actually an object and you are accessing the 
public constant value that represents the length of the array. In IDE, when we type object of a class and after that dot(.) 
they give some suggestion those suggestion is called Attribute. 
-  Method: Collection of statements, collected in a group for perform certain action. 
Two parts: method declation(access m., return type, name, param.)(method signature=name+parameters), method body. 
A method is a block of code which only runs when it is called. You can pass data, known as parameters, into a method. 
Methods are used to perform certain actions, and they are also known as functions. Why use methods? 
To reuse code: define the code once, and use it many times. A method must be declared within a class.

#### 21. Could we access a static variable (or method) from a non-static method? Why?

Non-static methods can access any static method and static variable also, without using the object of the class. 
Yes, because of static members i.e. both static variable and static methods belong to a class and can be 
called from anywhere, depending upon their access modifier (public, private).

#### 22. Could we access a non-static variable (or method) from a static method? Why?

You cannot access a non-static variable from a static method without an instance, because they doesn’t exist without 
their dad (the instance).

#### 23. How many instances you have of a static variable of a given class?

Only one. Static variables are also known as Class Variables.

#### 24. Why is it not a good practice to write a lot of static methods?

Interfaces and abstract classes only define non-static methods. Static methods don't fit very well into inheritance. 
Static methods do not have access to "super", which means that static methods cannot be overridden in any real sense. 
Actually, they can't be overridden at all, only hidden. (you should reserve use of static methods for those instances 
where you really want the Class object to own the method)

#### 25. What are the features of static attributes and static methods of a class? What are the benefits, when to use them?

Static members belong to the class instead of a specific instance, this means if you make a member static, you can 
access it without object. They can be accessed directly in static and non-static methods. Use static variables when: 
The value of the variable is independent of the objects (not unique for each object). E.g. number of students.

#### 26. What is the ‘this’ reference?

‘this’ is a reference variable that refers to the current object.

#### 27. What are base class, subclass and superclass?

In Java, it is possible to inherit attributes and methods from one class to another. We group the "inheritance concept" 
into two categories: subclass (child) - the class that inherits from another class superclass (parent class, base class)
 - the class being inherited from To inherit from a class, use the extends keyword.

#### 28. Draw an object oriented family (as entities, with relations) on the whiteboard.
<img src="/static/img/TherapyCenter.png" alt="classdiagram.png" sizes="20x20">

#### 29. Difference between overloading and overriding?

Overloading happens at compile-time while Overriding happens at runtime: The binding of overloaded method call to its 
definition has happens at compile-time however binding of overridden method call to its definition happens at runtime. 
Static methods can be overloaded which means a class can have more than one static method of same name. 
Static methods cannot be overridden, even if you declare a same static method in child class it has nothing to do 
with the same method of parent class. The most basic difference is that overloading is being done in the same class 
while for overriding base and child classes are required. Overriding is all about giving a specific implementation 
to the inherited method of parent class. Static binding is being used for overloaded methods and dynamic binding 
is being used for overridden/overriding methods. Argument list should be different while doing method overloading. 
Argument list should be same in method Overriding.

#### 30. What are the Object Oriented Principles? Explain the concepts with realistic examples!

-   Encapsulation Encapsulation is a process of wrapping code and data together into a single unit. Encapsulation in 
Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. 
In encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the 
methods of their current class. Therefore, it is also known as data hiding. To achieve encapsulation in Java: 
Declare the variables of a class as private. Provide public setter and getter methods to modify and view 
the variables values. The main difference between data hiding and encapsulation is that data hiding focus more on 
data security and encapsulation focuses more on hiding the complexity of the system.
-   Inheritance Inheritance is a mechanism in which one object acquires all the states and behaviors of a parent object. 
-   Abstraction Abstraction is a process of hiding the implementation details and showing only functionality to the user. 
-   Polymorphism Polymorphism is the ability of an object to take on many forms. Polymorphism in OOP occurs when 
a super class references a sub class object.

#### 31. What is method overloading?

A feature that allows a class to have more than one method having the same name, if their argument lists are different. 
(It is similar to constructor overloading in Java.)

Method overloading is an example of Static Polymorphism. Static Polymorphism is also known as compile time binding 
or early binding. Static binding happens at compile time. Method overloading is an example of static binding where 
binding of method call to its definition happens at Compile time.

#### 32. What is method overriding?

Declaring a method in sub class which is already present in parent class is known as method overriding. 
Overriding is done so that a child class can give its own implementation to a method which is already provided by 
the parent class. In this case the method in parent class is called overridden method and the method in child class 
is called overriding method.

Method Overriding is an example of runtime polymorphism. When a parent class reference points to the child class 
object then the call to the overridden method is determined at runtime, because during method call which method 
(parent class or child class) is to be executed is determined by the type of object.

#### 33. Explain how object oriented languages attempt to simplify memory management for Programmers.

In Java, memory management is the process of allocation and de-allocation of objects, called Memory management. 
Java does memory management automatically. Java uses an automatic memory management system called a garbage collector. 
Thus, we are not required to implement memory management logic in our application. Java memory management divides 
into two major parts: JVM Memory Structure Working of the Garbage Collector

#### 34. Explain the “Single Responsibility” principle!

The single-responsibility principle (SRP) is a computer-programming principle that states that every module or class 
should have responsibility over a single part of the functionality provided by the software, and that responsibility 
should be entirely encapsulated by the class, module or function. All its services should be aligned with that 
responsibility. They define responsibility as a reason to change. 
Eg. DatabaseManager - communication with DB, DaoJDBC, DaoMemory interfaces - save/load from DB

SOLID principles
S - Single-responsibility principle
A class should only have a single responsibility, that is, only changes to one part of the 
software's specification should be able to affect the specification of the class.
O - Open–closed principle
"Software entities ... should be open for extension, but closed for modification."
L - Liskov substitution principle
"Objects in a program should be replaceable with instances of their subtypes without altering the 
correctness of that program." See also design by contract.
I - Interface segregation principle
"Many client-specific interfaces are better than one general-purpose interface."
D - Dependency inversion principle
One should "depend upon abstractions, [not] concretions."

#### 35. What is an object oriented program? Explain, show.

Classes and objects are the two main aspects of object-oriented programming. 
Class – Fruit, Objects – Apple, Orange, Mango So, a class is a template for objects, and an object is an instance of a class. 
When the individual objects are created, they inherit all the variables and methods from the class. 
Encapsulation Encapsulation is a process of wrapping code and data together into a single unit.
Inheritance Inheritance is a mechanism in which one object acquires all the states and behaviors of a parent object. 
Abstraction Abstraction is a process of hiding the implementation details and showing only functionality to the user. 
Polymorphism Polymorphism is the ability of an object to take on many forms. 
Polymorphism in OOP occurs when a super class references a sub class object.

#### 36. How do you make a class immutable? What do you need to watch out for?

What do you need to watch out for? Declare the class as final so it can’t be extended. 
Make all fields private so that direct access is not allowed. Don’t provide setter methods for variables. 
Make all mutable fields final so that its value can be assigned only once. Initialize all the fields via a 
constructor performing deep copy. Perform cloning of objects in the getter methods to return a copy rather than 
returning the actual object reference.

#### 37. How many instances can be created for an abstract class?

0 An abstract class must be declared with an abstract keyword. It can have abstract and non-abstract methods. 
It cannot be instantiated. It can have constructors and static methods also. 
It can have final methods which will force the subclass not to change the body of the method.

## Programming languages

### Java

#### 38. What is autoboxing and unboxing?

-   Autoboxing: Converting a primitive value into an object of the corresponding wrapper class is called autoboxing. 
For example, converting int to Integer class. 
-   Unboxing: Converting an object of a wrapper type to its corresponding primitive value is called unboxing. 
For example conversion of Integer to int.

These techniques let us use primitive types and Wrapper class objects interchangeably and we do not need 
to perform any typecasting.

#### 39. If you have a variable, that shall store a positive whole number between 0 and 200, what primitive type would you use to store it?

int (minimum value of -231 and a maximum value of 231-1) (You can use a short to save memory in large arrays, 
in situations where the memory savings actually matters.)

#### 40. What is the "golden rule" of variable scoping in Java? What is the lifetime of variables?

The part of the program where the variable is accessible.
Class scope: Each variable declared inside of a class's brackets ( {} ) with private access modifier but outside 
of any method, has class scope. These variables can be used everywhere in the class, but not outside of it. 
Marked static is known as a class variable, and the lifetime of a class variable is until the end of the program or 
as long as the class is loaded in memory. Not marked with static: is an instance variable, it’s lifetime 
is until the object stays in memory.
Local variables: any other variables, lifetime of a local variable is until the control leaves the block 
in which it is declared.
Method Scope: When a variable is declared inside a method, it has method scope and it will only be valid 
inside the same method
Loop Scope: If we declare a variable inside a loop, it will have a loop scope and will only be available inside the loop.
Bracket Scope: We can define additional scopes anywhere using brackets ({}):

#### 41. What is the purpose of the ‘equals()’ method?

equals() is about content comparison (not reference comparison).

All classes in Java inherit from the Object class, it has basic methods like clone(), toString(), equals(). 
We can override the equals method in our class to check whether two objects have same data or not.
As a side note, when we override equals(), it is recommended to also override the hashCode() method. 
If we don’t do so, equal objects may get different hash-values; and hash based collections, including HashMap, 
HashSet, and Hashtable do not work properly.

#### 42. What is the difference between '==' and 'equals()'?

Main difference between .equals() method and == operator is that one is method and other is operator.
We can use == operators for reference comparison (address comparison) and .equals() method for content comparison. 
In simple words, == checks if both objects point to the same memory location whereas .equals() evaluates 
to the comparison of values in the objects.
If a class does not override the equals method, then by default it uses equals(Object o) method of the 
closest parent class that has overridden this method. 
We can apply equality operators for every primitive types including boolean type, we can also apply equality 
operators for object types.

#### 43. What does the ‘static’ keyword mean?

Static is a modifier in method declaration.
Static methods are the methods in Java that can be called without creating an object of class. 
They are referenced by the class name itself or reference to the Object of that class.
Use static method when you have code that can be shared across all instances of the same class. 
They are basically used to access static field(s) of the class.
Static methods can access the static variables and static methods directly.
Static methods can’t access instance methods and instance variables directly. They must use reference to object. 
And static method can’t use this keyword as there is no instance for ‘this’ to refer to.

#### 44. Why is the main() method declared as static? Explain.

Java main() method is always static, so that compiler can call it without the creation
of an object or before the creation of an object of the class.
In any Java program, the main() method is the starting point from where compiler
starts program execution. So, the compiler needs to call the main() method.
If the main() is allowed to be non-static, then while calling the main() method JVM
has to instantiate its class.
While instantiating it has to call the constructor of that class, There will be
ambiguity if the constructor of that class takes an argument.
Static method of a class can be called by using the class name only without
creating an object of a class.
The main() method in Java must be declared public, static and void. If any of
these are missing, the Java program will compile but a runtime error will be
thrown.

#### 45. What is the default access modifier in a class?

When no access modifier is specified for a class, method or data member, accessible only within the same package.

#### 46. What is the JVM?

Java Virtual Machine.
It's an abstract computing machine, which is a platform-independent execution
environment that converts Java bytecode into machine language and executes it.

#### 47. What is the difference between the JRE and the JDK?

-   JRE: Java Runtime Environment, is a set of so ware tools for development of
Java applications. It combines the Java Virtual Machine (JVM), platform core
classes and supporting libraries. It is part of the Java Development Kit (JDK), but
can be downloaded separately. JRE was originally developed by Sun
Microsystems Inc., a wholly-owned subsidiary of Oracle Corporation. Also known
as Java runtime.

-   JDK: Java Development Kit is a so ware development environment used for
developing Java applications and applets. It includes the Java Runtime
Environment (JRE), an interpreter/loader (java), a compiler (javac), an archiver
(jar), a documentation generator (javadoc) and other tools needed in Java
development.

#### 48. What is the difference between long and Long?

'Long' is a Java class (and so it will inherit Object) or a reference type, so it can be
null while 'long' is a primitive type, which must have a value.
'Long' can be passed to a method that accepts an Object, Number, Long or long
parameter, while 'long' can be passed to a method that accept 'long' or 'Long'.
'Long' can be used as a generic parameter type, as well.
'Long' can be also serialized/deserialized via the java serialization mechanism.

#### 49. Can a long store bigger numbers than a Long?

No, both can store number in same range.

#### 50. What kind of packages do you know under java.util.* ? Bring at least 3 examples.

java.util.Arrays; java.util.Date; java.util.Random; java.util.Scanner;

#### 51. What are the access modifiers in Java? Which one could we use for class?

-   Default – No keyword required: When no access modifier is specified for a class, method or data member, 
accessible only within the same package.
-   Private: The methods or data members declared as private are accessible only within the class in which 
they are declared. Any other class of same package will not be able to access these members.
-   Protected: The methods or data members declared as protected are accessible within same package or 
sub classes in different package.
-   Public: has the widest scope among all other access modifiers. Public classes, methods or data members 
which are accessible from everywhere in the program. There is no restriction on the scope of a public data members.

#### 52. Can an “enum” contain methods in Java? Explain.

You can add methods to a Java enum too. Here is an example:

```java
public enum Level {
    HIGH
    (3), //calls constructor with value 3
    MEDIUM(2), //calls constructor with value 2
    LOW //calls constructor with value 1
    (1)
    ; // semicolon needed when fields / methods follow
    private final int levelCode;
    Level(int levelCode) {
        this.levelCode = levelCode;
    }
    public int getLevelCode() {
        return this.levelCode;
    }
}
```
You call a Java enum method via a reference to one of the constant values. Here is
Java enum method call example:

```java
Level level = Level.HIGH;
System.out.println(level.getLevelCode());
```

This code would print out the value 3 which is the value of the levelCode field for the
enum constant HIGH.

#### 53. When would you use a private/protected/public attribute? What is the difference?

They are the access modifiers. Private: accessible only within the same class. 
Protected: accessible within same package or sub classes in different package. Public: accessible from everywhere in the program

#### 54. How do you prevent developers from subclassing a class?

You can prevent a class from being subclassed by using the final keyword in the
class's declaration.

#### 55. How do you prevent developers from overriding a method in a subclass?

You can prevent a method from being overridden by subclasses by declaring it as a
final method.

#### 56. How do you prevent developers from changing the value of a variable?

You can prevent a value of a variable from changing by declaring it as a final variable.

#### 57. Think about money ;) How would you store a currency value, that shall support decimal parts? Think it through again, and try to think outside of the box!

Java has Currency class that represents the ISO 4217 currency codes. BigDecimal is
the best type for representing currency decimal values, but that is not a primitive
type (it is part of the Java standard library, however).

#### 58. What happens if you try to call something, that you have no access to, because of data hiding?

If we have no access to call stg because of data hiding, we receive an error when we try to
call it.

#### 59. What happens if you try to delete/drop an item from an array, while you are iterating over it?

Java arrays do not provide a direct remove method to remove an element. Arrays in
Java are static so the size of the arrays cannot change once they are instantiated.
Thus we cannot delete an element and reduce the array size.

#### 60. What happens if you try to delete/drop/add an item from a List, while you are iterating over it?

It is not recommended to use ArrayList.remove() when iterating over elements. This
may lead to ConcurrentModificationException (Refer this for a sample program with
this exception). When iterating over elements, it is recommended to use
Iterator.remove() method. Every item in a list lives at its own unique index; which are
in order, starting from 0. If we remove an item, any item with an index greater than
the one we've removed has now been shi ed down.

#### 61. What happens if you try to add an item to the end of an array, while you are iterating over it?

In java an array has a fix memory place, so a er we initialized it, we can not change
its size.

#### 62. If you need to access the iterator variable after a for loop, how would you do it?

I would use an instance variable or a class variable and save the iterators value in it, 
this way I can access it outside of the for loop.

#### 63. Which interfaces extend the Collection interface in Java. Which classes?

List
Classes: ArrayList, LinkedList, Vector
Queue
Classes: PriorityQueue
Set
Classes: HashSet, LinkedHashSet

#### 64. What is the connection between equals() and hashCode()? How are they used in HashMap?

You must override hashCode() in every class that overrides equals(). Failure to do so
will result in a violation of the general contract for Object.hashCode(), which will
prevent your class from functioning properly in conjunction with all hash-based
collections, including HashMap, HashSet, and Hashtable.
Collections such as HashMap and HashSet use a hashcode value of an object to
determine how it should be stored inside a collection, and the hashcode is used again
in order to locate the object in its collection.
Hashing retrieval is a two-step process:
1. Find the right bucket (using hashCode())
2. Search the bucket for the right element (using equals())

#### 65. What is the difference between checked exceptions and unchecked exceptions? Could you bring example for each?

Checked exceptions: is checked by the compiler at compilation-time, so they also
called as compile time exceptions. These cannot simply be ignored, the
programmer should take care of these.
ClassNotFoundException
IOException
SQLException
FileNotFoundException
Unchecked exceptions: it occurs at the time of execution, so they also called as
Runtime exceptions. These includes programming bugs as logic errors or
improper use of an API. Runtime exceptions are ignored at the time of
compilation.
NullPointerException
ArrayIndexOutOfBoundsException
ClassCastException

#### 66. What is Error in Java and how does it relate to Exception?

All exception classes are subtypes of the java.lang.Exception class. The exception
class is a subclass of the Throwable class. Other than the exception class there is
another subclass called Error which is derived from the Throwable class.
Error: An Error indicates serious problem that a reasonable application should not try
to catch. (e.g.: JVM is out of memory.)
Exception: Exception indicates conditions that a reasonable application might try to
catch.

#### 67. When does 'finally' block run? What it is used for? Could you give an example from your projects when you would use 'finally'?

Java try block is used to enclose the code that might throw an exception. It must be
used within the method. If an exception occurs at the particular statement of try
block, the rest of the block code will not execute. Java try block must be followed by
either catch or finally block. The finally block always executes when the try block
exits. The finally block is a key tool for preventing resource leaks. When closing a file
or otherwise recovering resources, place the code in a finally block to ensure that
resource is always recovered.
The following finally block for the writeList method cleans up and then closes the
PrintWriter:

``` java
finally {
if ( out != null) {
System. out .println("Closing PrintWriter");
out .close();
} else {
System. out .println("PrintWriter not open");
}
}
```

#### 68. What is the largest number you can work with in Java?

Long.MAX_VALUE is 9,223,372,036,854,775,807

#### 69. When you use method overriding, can you change the access level of the method, from protected to public? Why?When you use method overriding, can you change the access level of the method, from public to protected? Why?

There is only one rule while doing Method overriding with Access modifiers:
If you are overriding any method, overridden method (i.e. declared in subclass)
must not be more restrictive.
(Access modifier restrictions in decreasing order: private > default > protected >
public)

#### 70. Can the main method be overridden? Explain your answer!

No, we cannot override main method of java because a static method cannot be
overridden.

#### 71. When you use method overriding, can you throw fewer exceptions in the subclass than in the parent class? Why?

No!
Rule: If the superclass method declares an exception, subclass overridden method
can declare same, subclass exception or no exception but cannot declare parent
exception.
Example in case subclass overridden method declares parent exception:

``` java
import java . io .*;
class Parent{
void msg() throws ArithmeticException { System. out .println
}
class TestExceptionChild2 extends Parent{
void msg() throws Exception { System. out .println("child");
public static void main(String args []){
Parent p = new TestExceptionChild2();
try{
p .msg();
} catch(Exception e ) {}
}
}
```

#### 72. When you use method overriding, can you throw more exceptions in the subclass than in the parent class? Why?

Yes!
Rule: If the superclass method declares an exception, subclass overridden method
can declare same, subclass exception or no exception but cannot declare parent
exception.
Example in case subclass overridden method declares subclass exception:

``` java
import java . io .*;
class Parent{
void msg() throws Exception { System. out .println("parent")
}
class TestExceptionChild4 extends Parent {
void msg() throws ArithmeticException { System. out .println
public static void main(String args []) {
Parent p = new TestExceptionChild4();
try {
p .msg();
} catch(Exception e ) {}
}
}
```

#### 73. What does "final" mean in case of a variable, method or a class?

final variable: If a variable is declared with the final keyword, its value cannot be
changed once initialized. To create constant variables.
final method: You use the final keyword in a method declaration to indicate that
the method cannot be overridden by subclasses.
final class: To prevent inheritance, final classes cannot be extended. For example,
all Wrapper Classes like Integer, Float etc. are final classes. We can not extend
them. The other use of final with classes is to create an immutable class like the
predefined String class. You can not make a class immutable without making it
final.

#### 74. What is the super keyword?

superclass (parent class, base class) - the class being inherited from
Usage of Java super Keyword
super can be used to refer immediate parent class instance variable.
super can be used to invoke immediate parent class method.
super() can be used to invoke immediate parent class constructor.

#### 75. What are “generics”? When to use? Show examples.

The idea is to allow type (Integer, String, etc and user defined types) to be a
parameter to methods, classes and interfaces. Generics are commonly used to create
type-safe collections for both reference and value types. For instance, a programmer
writes a generic method for sorting an array of objects. Generics allow the
programmer to use the same method for Integer arrays, Double arrays, and even
String arrays.

#### 76. What is the benefit of having “generic” containers?

Java Generics helps the programmer to reuse the code for whatever type he/she wishes.

#### 77. Given two Java programs on two different machines. How can you communicate between the two? What are the possible ways?

Platform independent, if the both machines has Java and they have TCP/IP connection or internet connection, they send the data by any service description language eg. JSON.
Java Socket programming is used for communication between the applications
running on di erent JRE. Java Socket programming can be connection-oriented or
connection-less. Socket and ServerSocket classes are used for connection-oriented
socket programming and DatagramSocket and DatagramPacket classes are used for
connection-less socket programming.
The client in socket programming must know two information: IP Address of Server,
and Port number.

#### 78. What is an annotation? What can be annotated and how? Show examples.

In the Java computer programming language, an annotation is a form of syntactic
metadata that can be added to Java source code. An annotation always starts with
the symbol @ followed by the annotation name. The symbol @ indicates to the
compiler that this is an annotation. Classes, methods, variables, parameters and Java
packages may be annotated.(Built-in annotations: @Test, @Override, @SuppressWarnings)

### Database

#### 79. How can you connect your application to a database server? What are the possible ways?

Using JDBC API and registering your DB class and making the connection. -Using
Datasource, where you define DB details on your server like WebSphere or Weblogic
server And you lookup the defined datasource. -Using some ORM framework like
Hibernate.

#### 80. What do you know about database normalization?

Normalization is the process of organizing data in a database. This includes creating
tables and establishing relationships between those tables according to rules
designed both to protect the data and to make the database more flexible by
eliminating redundancy and inconsistent dependency.


### C&#35;

#### Explain the purpose of IL and how does it relate to CLR?
#### What does “managed code” mean?
#### What is an assembly?
#### What is the difference between an EXE and a DLL?
#### What is strong-typing versus weak-typing? Which is preferred? Why?
#### What is a namespace?
#### Explain sealed class in C#?
#### What is explicit vs. implicit conversion? Give examples of both of them.
#### Is a struct stored on the heap or stack?
#### Can a struct have methods?
#### Can DateTimes be null?
#### List out the differences between Array and ArrayList in C#?
#### How is the using() pattern useful? What is IDisposable? How does it support deterministic finalization?
#### How can you make sure that objects using dedicated resources (database connection, files, hardware, OS handle, etc.) are released as early as possible?
#### Why to use keyword “const” in C#? Give an example.
#### What is the difference between “const” and “readonly” variables in C#?
#### What is a property in C#?
#### List out two different types of errors in C#?
#### What is the difference between “out” and “ref” parameters in C#?
#### Can we override private virtual method in C#?
#### What's the difference between IEquatable and just overriding Object.Equals()?
#### Explain the differences between public, protected, private and internal. Explain access modifier – “protected internal” in C#!
#### What’s the difference between using `override` and `new` keywords when defining method in child class?
#### Explain StringBuilder class in C#!
#### How we can sort the array elements in descending order in C#?
#### Can you use a value type as a generic type argument in C#? For example when implementing an interface like (IEquatable).
#### What are Nullable Types in C#?
#### Conceptually, what is the difference between early-binding and late-binding?
#### What is delegate, event, callback, multicast delegate?
#### What is enum in C#?
#### What is null-conditional operator?
#### What is null-coalescing operator?
#### What is serialization?
#### What is the difference between Finalize() and Dispose() methods?
#### How do you inherit a class from another class in C#?
#### What is difference between “is” and “as” operators in C#?
#### What are indexers in C# .NET?
#### What is the difference between returning IQueryable<T> vs. IEnumerable<T>?
#### What is LINQ? Explain the idea of extension methods.
#### What are the advantages and disadvantages of lazy loading?
#### How to use of “yield” keyword? Mention at least one practical scenario where it can be used?
#### What are attributes in C#? Give some examples of usage of them.
#### By what mechanism does NUnit know what methods to test?
#### What is the GAC? What problem does it solve?
#### What is the largest number you can work with in C#?

