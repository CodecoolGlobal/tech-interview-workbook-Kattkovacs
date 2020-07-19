OOP questions

Software design

Error handling (1)

What does 'fail fast' mean in terms of exception handling? Why is it a good practice?
In systems design, a fail-fast system is one which immediately reports at its interface any condition that is likely to indicate a failure. Fail-fast systems are usually designed to stop normal operation rather than attempt to continue a possibly flawed process. Such designs often check the system's state at several points in an operation, so any failures can be detected early. The responsibility of a fail-fast module is detecting errors, then letting the next-highest level of the system handle them.

Computer Science

Data structures (5)

How to find the middle element of singly linked list in O(n)?
Big O notation is a mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity. / Big O notation, indicating the order of growth of some quantity as a function of n or the limiting behavior of a function.
A/ Traverse the whole linked list and count the no. of nodes. Now traverse the list again till count/2
B/ Traverse linked list using two pointers. Move one pointer by one and other pointer by two. When the fast pointer reaches end slow pointer will reach middle of the linked list.
C/ Initialize mid element as head and initialize a counter as 0. Traverse the list from head, while traversing increment the counter and change mid to mid->next whenever the counter is odd. So the mid will move only half of the total length of the list.
Given an array of integers going from 1 to 100 (both inclusive) there is a duplicated entry. How to find it?

What is a linked list? How to find if a linked list has a loop?
The LinkedList data structure is a linear data structure where the elements are not stored in contiguous locations and every element is a separate object with a data part and address part. The elements are linked using pointers and addresses. Each element is known as a node. Due to the dynamicity and ease of insertions and deletions, they are preferred over the arrays. It also has few disadvantages like the nodes cannot be accessed directly instead we need to start from the head and follow through the link to reach to a node we wish to access.
Linked List is a part of the Collection framework present in java.util package. 
find if a linked list has a loop:
1. Hashing - HashSet<Node> s = new HashSet<Node>(); 
Traverse the list one by one and keep putting the node addresses in a Hash Table. At any point, if NULL is reached then return false and if next of current node points to any of the previously stored nodes in Hash then return true.
2. Modifying the linked list data-structure
Have a visited flag with each node. Traverse the linked list and keep marking visited nodes. If you see a visited node again then there is a loop. This solution works in O(n) but requires additional information with each node.
A variation of this solution that doesn’t require modification to basic data structure can be implemented using a hash, just store the addresses of visited nodes in a hash and if you see an address that already exists in hash then there is a loop.
3: Fastest: Floyd’s Cycle-Finding Algorithm
Traverse linked list using two pointers.
Move one pointer(slow_p) by one and another pointer(fast_p) by two.
If these pointers meet at the same node then there is a loop. If pointers do not meet then linked list doesn’t have a loop.

What is the Big O time complexity of the common operations in an ArrayList, LinkedList, HashMap? And of a bubble sort, quicksort, finding items in a Binary Search tree?
Big O Notation is a mathematical function used in computer science to describe how complex an algorithm is — or more specifically, the execution time required by an algorithm. In software engineering, it’s used to compare the efficiency of different approaches to a problem.
With Big O Notation, you express the runtime in terms of how quickly it grows relative to the input, as the input gets arbitrarily large. Essentially, it’s a way to draw insights into how scalable an algorithm is. It doesn’t tell you how fast or how slow an algorithm will go, but instead about how it changes with respect to its input size.
Big O time complexity = Worst Case Time Complexity [ Big-O ]
Common varieties of Big O Notation
O(1) - Constant time complexity: This translates to a constant runtime, meaning, regardless of the size of the input, the algorithm will have the same runtime.
O(log n) - Logarithmic time complexity: O(log n) means that time goes up linearly, while the n goes up exponentially. So if it takes 1 second to compute 10 elements, it will take 2 seconds to compute 100 elements and so on. It is O(log n) when we use divide and conquer algorithms e.g binary search.
O(n) - Linear time complexity: O(n) describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set.
ArrayList: add(), get() - O(1), We have to iterate the entire array: remove(), indexOf(), contains() - O(n)
LinkedList (linear data structure): add() - O(1), get() - O(n), remove() - O(1), contains() - O(n)
HashMap: insert and retrieve a value is O(1) on average (faster than lists)
Bubble sort: O(n2)
Quicksort: O(log(n))
Finding items in a Binary Search tree: O(log n)
(There’s a fine cheatsheet about all type of complexity of Data Structures and algorithms.)


How does HashMap work?
Hashing: It is the process of converting an object into an integer value. The integer value helps in indexing and faster searches.
HashMap is a part of the Java collection framework. It uses a technique called Hashing. It implements the map interface. It stores the data in the pair of Key and Value. HashMap contains an array of the nodes, and the node is represented as a class. It uses an array and LinkedList data structure internally for storing Key and Value. Map stores the data using hashcode() and equals() method from key.
HashMap<String, Integer> map = new HashMap<>();
map.put("Aman", 19);
hashCode(Key): This is the method of the object class. It returns the memory reference of the object in integer form.

Why is it important for keys in a map to have an immutable type? (Consider String for example.)
There is an Employee class (mutable) which we want to use as a key in Hashmap. With this mutable class we create an instance of Employee and put it in a hashmap: Employee key = new Employee("name1", "id1"); hashmap.put(key, "some value"); Let's assume that it has generated some hashcode like 123456 for given name and id, and it has calculated the index as 1 basis on that & then stored the value at related location. Now we call the setter on name or id on object "key" and it's hashcode is changed, let's assume now it has hashcode as 234567 and index position as 4. for ex: key.setName("other name");If we try to search the map for this key, it may not find a value as it's hashcode is changed and hashmap has calculated different index position for this key.
Now if we call the put() method on map with this key, it will store this object at different position and bucket in the hashmap. It may result in some memory leak as we still have the same employee object (key) as a key in map with the previous hashcode 123456.


Other (1)

What is a garbage collector, in a nutshell?
In computer science, garbage collection (GC) is a form of automatic memory management. The garbage collector, or just collector, attempts to reclaim garbage, or memory occupied by objects that are no longer in use by the program. 

Programming paradigms

Procedural (2)

What is casting? What is the difference between up vs downcasting?
Casting means picking an Object of one specific type and making it into another Object type. 
This process is called casting a variable. Like otherwise, it refers to the change of one data type to another. When you cast a particular variable, the data type of the variable itself will not get altered. Lets see with an example, in the following code, when we cast, num1 to a double; the variable num1 will not alter its data type from int to double. Alternatively, another new copy of num1 is built and its data type is turns as double.
	int num1=3, num2=4;
	double result = (double) num1 / num2;
Upcasting is casting a subtype to a supertype, upward to the inheritance tree. Let’s see an example: 
	Dog dog = new Dog();
	Animal anim = (Animal) dog;
	anim.eat();
or
	Animal anim = new Dog();
Here, we cast the Dog type to the Animal type. Because Animal is the supertype of Dog, this casting is called upcasting. Note that the actual object type does not change because of casting. The Dog object is still a Dog object. Only the reference type gets changed. 

Upcasting is always safe, as we treat a type to a more general one. In the above example, an Animal has all behaviors of a Dog.
Generally, upcasting is not necessary. 
Downcasting is casting to a subtype, downward to the inheritance tree. 
	Animal anim = new Cat();
	Cat cat = (Cat) anim;
Here, we cast the Animal type to the Cat type. As Cat is subclass of Animal, this casting is called downcasting.
Downcasting can fail if the actual object type is not the target object type. 
	Animal anim = new Cat();
	Dog dog = (Dog) anim;
This will throw a ClassCastException because the actual object type is Cat. And a Cat is not a Dog so we cannot cast it to a Dog.
The Java language provides the instanceof (operator) keyword to check type of an object before casting. 
Use downcasting when we want to access specific behaviors of a subtype.

Which order should we catch the exceptions? Why?
The order is whatever matches first, gets executed.
If the first catch matches the exception, it executes, if it doesn't, the next one is tried and on and on until one is matched or none are.
So, when catching exceptions you want to always catch the most specific first and then the most generic (as RuntimeException or Exception). It's also a compilation error to catch a generic exception first and then one of it's descendants later ( compilation error: first Exception, next RuntimeException). 


Object-oriented (26)

What is a class?
In object-oriented programming, a class is an extensible program-code-template for creating objects, providing initial values for state (member variables) and implementations of behavior (member functions or methods).In many languages, the class name is used as the name for the class (the template itself), the name for the default constructor of the class (a subroutine that creates objects), and as the type of objects generated by instantiating the class.

When an object is created by a constructor of the class, the resulting object is called an instance of the class, and the member variables specific to the object are called instance variables, to contrast with the class variables shared across the class.

What is an object?
In the class-based and object-oriented programming paradigms, object refers to a particular instance of a class, where the object can be a combination of variables, functions, and data structures. An object is an abstract data type with the addition of polymorphism and inheritance.

What is a constructor?
In class-based object-oriented programming, a constructor is a special type of subroutine called to create an object. It prepares the new object for use, often accepting arguments that the constructor uses to set required member variables.
A constructor resembles an instance method, but it differs from a method in that it has no explicit return type, it is not implicitly inherited and it usually has different rules for scope modifiers. Constructors often have the same name as the declaring class. They have the task of initializing the object's data members and of establishing the invariant of the class, failing if the invariant is invalid. A properly written constructor leaves the resulting object in a valid state. Immutable objects must be initialized in a constructor.
Most languages allow overloading the constructor in that there can be more than one constructor for a class, with differing parameters.
In Java, constructors differ from other methods in that:
Constructors never have an explicit return type.
Constructors cannot be directly invoked (the keyword “new” invokes them).
Constructors cannot be synchronized, final, abstract, native, or static.
It should not contain modifiers
Java constructors perform the following tasks in the following order:

1/ Call the default constructor of the superclass if no constructor is defined.
2/ Initialize member variables to the specified values.
3/ Executes the body of the constructor.

Do we require parameter for constructors?
There are two type of constructor in Java:
	No-argument constructor: A constructor that has no parameter is known as default constructor. If we don’t define a constructor in a class, then compiler creates default constructor(with no arguments) for the class. 
	Parameterized Constructor: A constructor that has parameters is known as parameterized constructor. If we want to initialize fields of the class with your own values, then use a parameterized constructor.
class Geek 
{ 
    String name; 
    int id; 

    Geek(String name, int id) 
    { 
        this.name = name; 
        this.id = id; 
    } 
} 

What is an interface?
An interface is a contract between a class and the outside world. When a class implements an interface, it promises to provide the behavior published by that interface. In its most common form, an interface is a group of related methods with empty bodies. If your class claims to implement an interface, all methods defined by that interface must appear in its source code before the class will successfully compile.

What are access modifiers?
Access level modifiers determine whether other classes can use a particular field or invoke a particular method. There are two levels of access control:

- At the top level—public, or package-private (no explicit modifier).
- At the member level—public, private, protected, or package-private (no explicit modifier).
A class may be declared with the modifier public, in which case that class is visible to all classes everywhere. If a class has no modifier (the default, also known as package-private), it is visible only within its own package.

At the member level, you can also use the public modifier or no modifier (package-private) just as with top-level classes, and with the same meaning. For members, there are two additional access modifiers: private and protected. The private modifier specifies that the member can only be accessed in its own class. The protected modifier specifies that the member can only be accessed within its own package (as with package-private) and, in addition, by a subclass of its class in another package.

What is data hiding?
Encapsulation is one of the four fundamental OOP concepts. The other three are inheritance, polymorphism, and abstraction.
Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. In encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class. Therefore, it is also known as data hiding.
To achieve encapsulation in Java:
- Declare the variables of a class as private.
- Provide public setter and getter methods to modify and view the variables values.

Can a static method use non-static members?
In static method, the method can only access only static data members and static methods of another class or same class but cannot access non-static methods and variables.

What is the difference between hiding a static method and overriding an instance method?
Instance methods and class methods have this important difference in behavior, we use different terms - "overriding" for instance methods and "hiding" for class methods - to distinguish between the two cases. And when we say you can't override a static method, what that means is that even if you write code that looks like it's overriding a static method (like the first Foo and Bar at the top of this page) - it won't behave like an overridden method, because the compiler only uses the declared type of the reference. That's what we mean when we say a static method does not have run-time polymorphism.

Define the following terms: Instantiation:
In object-oriented programming, an object is an instance of a class. Creating a new instance of that class is instantiation.
Attribute:
An attribute is another term for a field. It’s typically a public field that can be accessed directly. Let’s see a particular case of Array, the array is actually an object and you are accessing the public constant value that represents the length of the array.
In IDE, when we type object of a class and after that dot(.) they give some suggestion those suggestion is called Attribute.
Method: 
A method is a block of code which only runs when it is called.
You can pass data, known as parameters, into a method.
Methods are used to perform certain actions, and they are also known as functions.
Why use methods? To reuse code: define the code once, and use it many times.
A method must be declared within a class.

Could we access a static variable (or method) from a non-static method? Why?
Non-static methods can access any static method and static variable also, without using the object of the class.
Yes, because of static members i.e. both static variable and static methods belong to a class and can be called from anywhere, depending upon their access modifier (public, private).

Could we access a non-static variable (or method) from a static method? Why?
You cannot access a non-static variable from a static method without an instance, because they doesn’t exist without their dad (the instance).

How many instances you have of a static variable of a given class?
Only one.
Static variables are also known as Class Variables.

Why is it not a good practice to write a lot of static methods?
Interfaces and abstract classes only define non-static methods. Static methods don't fit very well into inheritance.
Static methods do not have access to "super", which means that static methods cannot be overridden in any real sense. Actually, they can't be overridden at all, only hidden. 
(you should reserve use of static methods for those instances where you really want the Class object to own the method)

What are the features of static attributes and static methods of a class? What are the benefits, when to use them?
Static members belong to the class instead of a specific instance, this means if you make a member static, you can access it without object. 
They can be accessed directly in static and non-static methods.
Use static variables when : The value of the variable is independent of the objects (not unique for each object). E.g. number of students.

What is the ‘this’ reference?
‘this’ is a reference variable that refers to the current object.

What are base class, subclass and superclass?
In Java, it is possible to inherit attributes and methods from one class to another. We group the "inheritance concept" into two categories:
subclass (child) - the class that inherits from another class
superclass (parent class, base class) - the class being inherited from
To inherit from a class, use the extends keyword.

Draw an object oriented family (as entities, with relations) on the whiteboard.


Difference between overloading and overriding?
Overloading happens at compile-time while Overriding happens at runtime: The binding of overloaded method call to its definition has happens at compile-time however binding of overridden method call to its definition happens at runtime.
Static methods can be overloaded which means a class can have more than one static method of same name. Static methods cannot be overridden, even if you declare a same static method in child class it has nothing to do with the same method of parent class.
The most basic difference is that overloading is being done in the same class while for overriding base and child classes are required. Overriding is all about giving a specific implementation to the inherited method of parent class.
Static binding is being used for overloaded methods and dynamic binding is being used for overridden/overriding methods.
Argument list should be different while doing method overloading. Argument list should be same in method Overriding.

What are the Object Oriented Principles? Explain the concepts with realistic examples!
Encapsulation
Encapsulation is a process of wrapping code and data together into a single unit.
Inheritance
Inheritance is a mechanism in which one object acquires all the states and behaviors of a parent object.
Abstraction
Abstraction is a process of hiding the implementation details and showing only functionality to the user.
Polymorphism
Polymorphism is the ability of an object to take on many forms.
Polymorphism in OOP occurs when a super class references a sub class object.

What is method overloading?
A feature that allows a class to have more than one method having the same name, if their argument lists are different. (It is similar to constructor overloading in Java.)

Method overloading is an example of Static Polymorphism. 
Static Polymorphism is also known as compile time binding or early binding.
Static binding happens at compile time. Method overloading is an example of static binding where binding of method call to its definition happens at Compile time.

What is method overriding?
Declaring a method in sub class which is already present in parent class is known as method overriding. Overriding is done so that a child class can give its own implementation to a method which is already provided by the parent class. In this case the method in parent class is called overridden method and the method in child class is called overriding method. 

Method Overriding is an example of runtime polymorphism. When a parent class reference points to the child class object then the call to the overridden method is determined at runtime, because during method call which method(parent class or child class) is to be executed is determined by the type of object. 


Explain how object oriented languages attempt to simplify memory management for Programmers.
In Java, memory management is the process of allocation and de-allocation of objects, called Memory management. Java does memory management automatically. Java uses an automatic memory management system called a garbage collector. Thus, we are not required to implement memory management logic in our application. Java memory management divides into two major parts:
JVM Memory Structure
Working of the Garbage Collector

Explain the “Single Responsibility” principle!
The single-responsibility principle (SRP) is a computer-programming principle that states that every module or class should have responsibility over a single part of the functionality provided by the software, and that responsibility should be entirely encapsulated by the class, module or function. All its services should be aligned with that responsibility. Martin defines a responsibility as a reason to change.

What is an object oriented program? Explain, show.
Classes and objects are the two main aspects of object-oriented programming.
Class – Fruit, Objects – Apple, Orange, Mango 
So, a class is a template for objects, and an object is an instance of a class.
When the individual objects are created, they inherit all the variables and methods from the class.
Encapsulation
Encapsulation is a process of wrapping code and data together into a single unit.
Inheritance
Inheritance is a mechanism in which one object acquires all the states and behaviors of a parent object.
Abstraction
Abstraction is a process of hiding the implementation details and showing only functionality to the user.
Polymorphism
Polymorphism is the ability of an object to take on many forms.
Polymorphism in OOP occurs when a super class references a sub class object.

How do you make a class immutable? What do you need to watch out for?
Declare the class as final so it can’t be extended.
Make all fields private so that direct access is not allowed.
Don’t provide setter methods for variables.
Make all mutable fields final so that its value can be assigned only once.
Initialize all the fields via a constructor performing deep copy.
Perform cloning of objects in the getter methods to return a copy rather than returning the actual object reference.

How many instances can be created for an abstract class?
0
An abstract class must be declared with an abstract keyword.
It can have abstract and non-abstract methods.
It cannot be instantiated.
It can have constructors and static methods also.
It can have final methods which will force the subclass not to change the body of the method.

Programming languages

Java (39)

What is autoboxing and unboxing?

If you have a variable, that shall store a positive whole number between 0 and 200, what primitive type would you use to store it?

What is the "golden rule" of variable scoping in Java? What is the lifetime of variables?

What is the purpose of the ‘equals()’ method?
What is the difference between '==' and 'equals()'?

What does the ‘static’ keyword mean?

Why is the main() method declared as static? Explain.

What is the default access modifier in a class?

What is the JVM?

What is the difference between the JRE and the JDK?

What is the difference between long and Long?
Can a long store bigger numbers than a Long?

What kind of packages do you know under java.util.* ? Bring at least 3 examples.

What are the access modifiers in Java? Which one could we use for class?

Can an “enum” contain methods in Java? Explain.

When would you use a private/protected/public attribute? What is the difference?

How do you prevent developers from subclassing a class?

How do you prevent developers from overriding a method in a subclass?

How do you prevent developers from changing the value of a variable?

Think about money ;) How would you store a currency value, that shall support decimal parts? Think it through again, and try to think outside of the box!

What happens if you try to call something, that you have no access to, because of data hiding?

What happens if you try to delete/drop an item from an array, while you are iterating over it?

What happens if you try to delete/drop/add an item from a List, while you are iterating over it?

What happens if you try to add an item to the end of an array, while you are iterating over it?

If you need to access the iterator variable after a for loop, how would you do it?

Which interfaces extend the Collection interface in Java. Which classes?

What is the connection between equals() and hashCode()? How are they used in HashMap?

What is the difference between checked exceptions and unchecked exceptions? Could you bring example for each?

What is Error in Java and how does it relate to Exception?

When does 'finally' block run? What it is used for? Could you give an example from your projects when you would use 'finally'?

What is the largest number you can work with in Java?

When you use method overriding, can you change the access level of the method, from protected to public? Why? When you use method overriding, can you change the access level of the method, from public to protected? Why?

Can the main method be overridden? Explain your answer!

When you use method overriding, can you throw fewer exceptions in the subclass than in the parent class? Why?

When you use method overriding, can you throw more exceptions in the subclass than in the parent class? Why?

What does "final" mean in case of a variable, method or a class?

What is the super keyword?

What are “generics”? When to use? Show examples.

What is the benefit of having “generic” containers?

Given two Java programs on two different machines. How can you communicate between the two? What are the possible ways?

What is an annotation? What can be annotated and how? Show examples.

Database (2)

How can you connect your application to a database server? What are the possible ways?

What do you know about database normalization?

# OOP questions

## Software design

### Error handling

#### What does 'fail fast' mean in terms of exception handling? Why is it a good practice?

## Computer Science

### Data structures

#### How to find the middle element of singly linked list in O(n)?
#### Given an array of integers going from 1 to 100 (both inclusive) there is a duplicated entry. How to find it?
#### What is a linked list? How to find if a linked list has a loop?
#### What is the Big O time complexity of the common operations in an ArrayList, LinkedList, HashMap? And of a bubble sort, quicksort, finding items in a Binary Search tree?
#### How does HashMap work?
#### Why is it important for keys in a map to have an immutable type? (Consider String for example.)

### Other

#### What is a garbage collector, in a nutshell?
In computer science, garbage collection (GC) is a form of automatic memory management. The garbage collector, or just collector, attempts to reclaim garbage, or memory occupied by objects that are no longer in use by the program. Garbage collection was invented by John McCarthy around 1959 to simplify manual memory management in Lisp.


## Programming paradigms

### Procedural

#### What is casting? What is the difference between up vs downcasting?
#### Which order should we catch the exceptions? Why?

### Object-oriented

#### What is a class?
#### What is an object?
#### What is a constructor?
#### Do we require parameter for constructors?
#### What is an interface?
#### What are access modifiers?
#### What is data hiding?
#### Can a static method use non-static members?
#### What is the difference between hiding a static method and overriding an instance method?
#### Define the following terms: Instantiation, Attribute, Method
#### Could we access a static variable (or method) from a non-static method? Why?
#### Could we access a non-static variable (or method) from a static method? Why?
#### How many instances you have of a static variable of a given class?
#### Why is it not a good practice to write a lot of static methods?
#### What are the features of static attributes and static methods of a class? What are the benefits, when to use them?
#### What is the ‘this’ reference?
#### What are base class, subclass and superclass?
#### Draw an object oriented family (as entities, with relations) on the whiteboard.
#### Difference between overloading and overriding?
#### What are the Object Oriented Principles? Explain the concepts with realistic examples!
#### What is method overloading?
#### What is method overriding?
#### Explain how object oriented languages attempt to simplify memory management for Programmers.
#### Explain the “Single Responsibility” principle!
#### What is an object oriented program? Explain, show.
#### How do you make a class immutable? What do you need to watch out for?
#### How many instances can be created for an abstract class?

## Programming languages

### Java

#### What is autoboxing and unboxing?
#### If you have a variable, that shall store a positive whole number between 0 and 200, what primitive type would you use to store it?
#### What is the "golden rule" of variable scoping in Java? What is the lifetime of variables?
#### What is the purpose of the ‘equals()’ method?
#### What is the difference between '==' and 'equals()'?
#### What does the ‘static’ keyword mean?
#### Why is the main() method declared as static? Explain.
#### What is the default access modifier in a class?
#### What is the JVM?
#### What is the difference between the JRE and the JDK?
#### What is the difference between long and Long?
#### Can a long store bigger numbers than a Long?
#### What kind of packages do you know under java.util.* ? Bring at least 3 examples.
#### What are the access modifiers in Java? Which one could we use for class?
#### Can an “enum” contain methods in Java? Explain.
#### When would you use a private/protected/public attribute? What is the difference?
#### How do you prevent developers from subclassing a class?
#### How do you prevent developers from overriding a method in a subclass?
#### How do you prevent developers from changing the value of a variable?
#### Think about money ;) How would you store a currency value, that shall support decimal parts? Think it through again, and try to think outside of the box!
#### What happens if you try to call something, that you have no access to, because of data hiding?
#### What happens if you try to delete/drop an item from an array, while you are iterating over it?
#### What happens if you try to delete/drop/add an item from a List, while you are iterating over it?
#### What happens if you try to add an item to the end of an array, while you are iterating over it?
#### If you need to access the iterator variable after a for loop, how would you do it?
#### Which interfaces extend the Collection interface in Java. Which classes?
#### What is the connection between equals() and hashCode()? How are they used in HashMap?
#### What is the difference between checked exceptions and unchecked exceptions? Could you bring example for each?
#### What is Error in Java and how does it relate to Exception?
#### When does 'finally' block run? What it is used for? Could you give an example from your projects when you would use 'finally'?
#### What is the largest number you can work with in Java?
#### When you use method overriding, can you change the access level of the method, from protected to public? Why?When you use method overriding, can you change the access level of the method, from public to protected? Why?
#### Can the main method be overridden? Explain your answer!
#### When you use method overriding, can you throw fewer exceptions in the subclass than in the parent class? Why?
#### When you use method overriding, can you throw more exceptions in the subclass than in the parent class? Why?
#### What does "final" mean in case of a variable, method or a class?
#### What is the super keyword?
#### What are “generics”? When to use? Show examples.
#### What is the benefit of having “generic” containers?
#### Given two Java programs on two different machines. How can you communicate between the two? What are the possible ways?
#### What is an annotation? What can be annotated and how? Show examples.

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

### Database

#### How can you connect your application to a database server? What are the possible ways?
#### What do you know about database normalization?
