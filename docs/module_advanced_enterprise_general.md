# General enterprise questions

## Software engineering

### Architectures

#### 1. What is n-tier (or multi-tier) architecture?

In software engineering, **multi-tier architecture** (often referred to as **n-tier architecture**) is a **client-server architecture** in which, the presentation, the application processing and the data management are logically separate processes. For example, an application that uses middleware to service data requests between a user and a database employs multi-tier architecture. The most widespread use of "multi-tier architecture" refers to three-tier architecture.

N-tier architecture is also called multi-tier architecture because the software is engineered to have the processing, data management, and presentation functions **_physically_ and logically separated**. That means that these different functions are **hosted on several machines** or clusters, ensuring that services are provided without resources being shared and, as such, these services are delivered at top capacity.

Not only does your software gain from being able to get services at the best possible rate, but it's also easier to manage. This is because when you work on one section, the changes you make will not affect the other functions. And if there is a problem, you can easily pinpoint where it originates.

Three tiers:

1. **Presentation tier**:
   The top-most level of the application is the **User Interface**. The main function of the interface is to translate tasks and result to something the user can understand.
2. **Logic tier**:
   This layer coordinates the application, processes commands, makes logical decisions and evaluations, and performs calculations. It also moves and processes data between two surrounding layers.
3. **Data tier**:
   Here information is stored and retrieved from a database or file system. The information is then passed back to the logic tier for processing, and then eventually back to the user.

**The separate physical location of these tiers is what differentiates n-tier architecture from the _model-view-controller_ framework that only separates presentation, logic, and data tiers _in concept_.** N-tier architecture also differs from MVC framework in that the former has a middle layer or a logic tier, which facilitates all communications between the different tiers. When you use the MVC framework, the interaction that happens is triangular; instead of going through the logic tier, it is the control layer that accesses the model and view layers, while the model layer accesses the view layer.

This is not to say that you can only use either the MVC framework or the n-tier architecture. There are a lot of software that brings together these two frameworks. For instance, you can use the n-tier architecture as the overall architecture, or use the MVC framework in the presentation tier.

Benefits: secure, easy to manage, scalable (between tiers), flexible (inside tiers), reusable code.

> There are n-tier architecture models that have more than three tiers. E.g.: Services + Business domain + Presentation tier + Client tier.

#### 2. What are microservices? Advantages and disadvantages?

#### 3. What is Separation of Concerns?

The **separation of concerns (SoC)** is one of the most fundamental principles in software development.

It is so crucial that 2 out of 5 SOLID principles (**Single Responsibility** and **Interface Segregation**) are direct derivations from this concept.

The principle is simple: don't write your program as one solid block, instead, **break up the code into chunks** that are finalized tiny pieces of the system each able to complete a simple distinct job.

#### 4. What is a layered design and why is it important in enterprise applications?

Modern enterprise applications can be large and daunting. The sheer amount of users, data, transactions, options, business cases, components, interacting systems, and a host of other factors, make designing business applications require a great deal of expertise. There are many examples of enterprise software that grew too complex, unmanageable, and fragile due to implementation, that did not account for change. It is for this reason that an effective enterprise application should be divided into layers.

The layered architecture is the simplest form of **software architectural pattern**. If you are going to design a rudimentary application where the user count is very low ( < 100–200 ) and you are sure that there won't be too much requirement changes after you go live, this is the best software architecture pattern to use.

Layered architecture patterns are **n-tiered patterns** where the components are organized in horizontal layers. All the **components are interconnected but do not depend on each other**.

There are 4 layers in this architecture. From top to bottom:

1. **Presentation layer**: It contains all categories related to the presentation layer.
2. **Business layer**: It contains business logic.
3. **Persistence layer**: Used for handling functions like object-relational mapping.
4. **Database layer**: This is where all the data is stored.

Pros:

- It is easy to test as components belong to specific layers. As such, they can be tested separately.
- It is simple and easy to implement because naturally, most applications work in layers.

Cons:

- Although changes can be done to a particular layer, it is not easy because the application is a singular unit. Also, the coupling between layers tends to make it harder. This also makes it difficult to scale.
- It must be deployed as a singular unit thus a **change to a particular layer means the whole system must be redeployed**.
- The larger is it, the more resources it requires for requests to go through multiple layers and thus will cause performance issues.

#### 5. What is Dependency Injection?

Classes have "dependencies" they call methods on. Most people call them "variables" or more precisely "instance variables".

You could set the dependency (variable) via a setter method or even via reflection, you should choose your way. But using constructors is the most popular one.

You can have the dependency be an interface or an abstract class and then polymorphically pass in some implementation.

Also DI facilitates a very important principle, **Separation of Concerns**, because:

- Many times is not a given class' responsibility to instantiate the things inside it.
- Your code will be more **modular**, as the outside world can decide what exactly it should be (to make it super modular you could make it an interface).

Dependency Injection can also refer to a **software library** that provides DI functionality and allows automating many of the tasks involved in Object Composition, Interception, and Lifetime Management. DI Containers are also known as Inversion of Control (IoC) Containers. (E.g. Spring Boot, ASP.NET Core).

At the very least, a DI Container allows **Auto-Wiring**, which is the ability to automatically compose an object graph from maps between **Abstractions** and concrete types by making use of the types' **metadata** (reflection?) supplied by the compiler and its runtime environment.

**This typically means that a DI Container will analyze a type's constructor and will inject dependencies into it, without the need of having to specify each constructor argument manually.**

#### 6. What is the DAO pattern? When and how to implement?

**Data access object (DAO)** is a pattern that provides an abstract interface to some type of database or other persistence mechanism.

By mapping application calls to the persistence layer, the DAO provides some specific data operations without exposing details of the database. This isolation supports the single responsibility principle.

It separates what data access the application needs from how these needs can be satisfied with a specific DBMS, database schema, etc.

#### 7. What is SOA? When to use?

Service-Oriented Architecture (SOA) is a style of software design where services are provided to the other components by application components, through a communication protocol over a network. Its principles are independent of vendors and other technologies, promotes loose coupling between components so that you can reuse them.

### Testing

#### 8. What are unit test, integration test, system test, regression test, acceptance test? What is the major difference between these?

**Testing methods**:

- **Black-box testing**: Testing the functionality of the software without knowing its internal code structure.
- **White-box testing**: Testing the software itself with the knowledge of its internal structure. Basically you know the code and write the tests to test the code.

**Levels of testing**:

1. **Unit test** -- Test individual component (**low-level**): Specify and test one point of the contract of **a single method** of a class. This should have a very narrow and well defined scope. Complex dependencies and interactions to the outside world are **stubbed** or **mocked**. Some characteristics:
   - examine a single class,
   - require **just the source code** of the application, instead of a running instance,
   - are **fast**,
   - are not affected by external systems, e.g. web services or databases, and
   - perform little or no I/O, e.g. no real database connections -- **no side-effects**.
   - **Positive Testing**: testing the system by giving the **valid data**.
   - **Negative Testing**: testing the system by giving the **invalid data**.
2. **Integration test** -- Test component groups: Test the correct inter-operation of multiple subsystems. There is whole spectrum there, from testing integration between two classes, to testing integration with the production environment.
3. **System test** -- Test the integrated System: Tests a system as a **black box**. Dependencies on other systems are often **mocked** or **stubbed** during the test (otherwise it would be more of an integration test).
4. **Acceptance test** -- Test the final System: Test that a feature or use case is correctly implemented. It is similar to an integration test, but with a **focus on the use case** to provide rather than on the components involved.

**Types of testing**:

- **Functional testing**:
  - Functional Testing is the type of testing done against the **business requirements** of application. It is a **black box type** of testing (mostly).
  - **Smoke test** (aka **sanity check**): A simple integration test where we just check that when the _system under test (SUT)_ is invoked it returns normally and does not blow up. Smoke testing is **an analogy with plumbing**, where a system of pipes is literally filled by smoke and then checked visually. If anything smokes, the system is leaky.
  - **Regression test**: A test that was written **when a bug was fixed**. It ensures that this specific bug will not occur again. The full name is "non-regression test". It can also be a test made **prior to changing an application** to make sure the application provides the same outcome.
- **Non-functional testing**:
  - Done against the **non functional requirements**. Most of the criteria are not consider in functional testing so it is used to check the readiness of a system.
  - Performance testing
  - Stress testing
  - Security testing
  - etc.

#### 9. What is code coverage? Why is it used? How you can measure?

Code Coverage is a measurement of how many lines/blocks/arcs of your code are executed while the automated tests are running.

While code coverage is a good metric of how much testing you are doing, it is not necessarily a good metric of how well you are testing your product. There are other metrics you should use along with code coverage to ensure the quality.

#### 10. What does mocking mean? How would you do it 'manually' (i. e. without using any fancy framework)?

Unit testing means testing units _independently_, so in some cases we need to isolate the component under test using what Martin Fowler calls **test doubles** (dummies, stubs, fakes, mocks).

In short, mocking is creating units (class instances) that **simulate the behaviour** of real units.

Mocking is the act of **removing external dependencies** from a unit test in order to **create a controlled environment** around it. Typically, we mock all other classes that interact with the class that we want to test. Common targets for mocking are:

- Database connections,
- Web services,
- Classes that are slow,
- Classes with side effects, and
- Classes with non-deterministic behavior.

Mocks and stubs are fake classes that replace these external dependencies. Most of the time, we're fine using only stubs.

**Stub**: A stub is a fake class that comes with **preprogrammed return values**. It's injected into the class (component) under test to give you absolute control over what's being tested as input. A typical stub is a **database connection** that allows you to mimic any scenario without having a real database.

**Mock**: A mock can be examined after the test is finished for its interactions with the class (component) under test. For example, you can ask it whether a method was called or how many times it was called. Typical mocks are **classes with side effects** that need to be examined, e.g. a class that sends emails or sends data to another external service.

We usually use libraries (Mockito, _NSubstitute_, Moq) that make mocking of objects easy. To make mocking possible you should use the **Dependency Injection** design pattern in your code!

Without a library, the easiest way would be to create an **inner class** that implements the interface, implement the methods to return the data that you want, then **use it in the test case**.

#### 11. What is a test case? What is an assertion? Give examples!

A test case is represented by a single test method. An assertion asserts that the _expected_ outcome is the same as the _actual_ outcome.

Example:

```csharp
[Test]
public void ReadLines_Given1And1_ShouldReturnFirstLine()
{
    // Arrange
    int fromLine = 1;
    int toLine = 1;
    _filePartReader.Setup(SHORT_FILE_PATH, fromLine, toLine);
    // Act
    string expected = TestUtils.NormalizeLineEnds("this is a sentence\n");
    string actual = TestUtils.NormalizeLineEnds(_filePartReader.ReadLines());
    // Assert
    Assert.AreEqual(expected, actual);
}
```

#### 12. What is TDD? What are the benefits?

**Test-driven development (TDD)** is a software development process that relies on the repetition of a very short development cycle:

1. requirements are turned into very specific test cases
2. then the code is created / improved so that the tests pass

Benefits:

- You get immediate feedback on if your code is working, so you can **find bugs faster**
- By seeing the test go from red to green, you know that you have both a working **regression test**, and working code
- You gain **confidence to refactor existing code**, which means you can clean up code without worrying what it might break
- At the end you have a suite of regression tests that can be run during automated builds to give you greater confidence that your codebase is solid

Other benefits:

- Better understanding of what you're going to write: When you write the test cases first, you think more critically about the _corner cases_. It's then easier to address them when you write the code and ensure that they're accurate.
- Enforces the policy of writing tests a little better
- Speeds up development in many cases

#### 13. What are the unit testing best practices? (Eg. how many assertion should a test case contain?)

- Never push a failing test to the repository.
- Use **separate folder for tests** as you might not want to deliver (ie. give to the user) your test along with the production code.
- Give **descriptive names** to test methods so that you can see what fails easier
- Write tests for the error cases and corner cases.
- Check only a single thing in one test method (practically: use **1 assert per test method**)
- Use assert (or expected exception) in all of the test methods.
- Use the expected result as the first argument of an assert method: `Assert.AreEqual(expected, actual);`
- Use the AAA pattern

#### What is arrange/act/assert pattern?

A **Unit Test** tests a single **"Act"** in a program, typically a single method call on an object instance. **Arrange, Act, Assert (AAA)** organizes a unit test into three parts: _before, during and after the Act_.

**Arrange**: Everything up to, but not including, the method call of interest. We set up the **state** that we want the world (the object that we're calling the method on, other objects that it interacts with, etc.) to be in when we call the method.

**Act**: The call of the method we're testing.

**Assert**: The rest of the test, where we Assert that the Act had the effects on the world that we expect.

### DevOps

#### 14. What is continuous integration? Why is CI important?

#### 15. Why are tests important in the CI workflow?

#### 16. Name some software that help the CI workflow!

#### 17. What is Continuous Delivery?

#### 18. What is Continuous Deployment?

#### 19. What is DevOps?

DevOps is a set of processes, methods and systems for communication, collaboration and integration between departments for Development (Applications/Software Engineering), Technology Operations and Quality Assurance (QA)

### Software Methodologies

#### 21. What kind of software-lifecycle models do you know?

- Agile development
- Waterfall model

#### 22. What is a UML diagram? What kind of diagram types do you know?

The **Unified Modeling Language** is a standard **visual modeling language** intended to be used for:

- Modeling business and similar processes,
- Analysis, design, and implementation of software-based systems

There are two major kinds of UML diagram, structure diagrams and behavior diagrams:

- **Structure diagrams**: show the **static structure** of the system and its parts on different abstraction and implementation levels and how they are related to each other. The elements in a structure diagram represent the meaningful concepts of a system, and may include abstract, real world and implementation concepts.
- **Behavior diagrams**: show the **dynamic behavior** of the objects in a system, which can be described as a series of changes to the system over time.

I've used **Class Diagrams** (structure) extensively, and **Sequence Diagrams** (behavior) occasionally.

> Draw.io > PlantUML

#### 23. What is a UML class diagram? What are the typical elements?

Before implementating a bunch of classes, you'll want to have **a conceptual understanding of the system** — that is, what classes do I need? What functionality and information will these classes have? How do they interact with one another? Who can see these classes? And so on.

That's where class diagrams come in. Class diagrams are a neat way of visualizing the classes in your system before you actually start coding them up. They're **a static representation of your system structure**.

Why do we need class diagrams:

1. **Planning** and modeling ahead of time make programming much easier.
2. Besides that, **making changes** to class diagrams is **easy**, whereas coding differnent functionality after the fact is kind of annoying.
3. When someone wants to build a house, they don't just grab a hammer and get to work. They need to have a **blueprint** — a design plan — so they can ANALYZE & modify their system.
4. You don't need much technical/language-specific knowledge to **understand** it.

**UML Class Notation**:

A class is represented as a box with **3 compartments**. The uppermost one contains the **class name**. The middle one contains the **STATE = class attributes** and the last one contains the **BEHAVIOR = class operations** (methods).
Each attribute has a _type_. Each operation has a _signature_.

**Class visibility**:

- \- private
- \# protected
- ~ package
- \+ public

**Relationships**:

- **Association**:
  - Associations are relationships between classes in a UML Class Diagram. They are represented by **a solid line between classes**. Associations are typically named using a verb or verb phrase which reflects the real world problem domain.
  - General association is simply a solid line.
  - E.g. `Airplane -- Ticket`
- **Generalization (inheritance)**:
  - Represents an **"is-a" relationship**.
  - An abstract class name is shown in italics.
  - Represented by **a solid line + an empty arrow** pointing to the **extended** class.
  - E.g. `Square --|> Rectangle`
- **Realization**:
  - Same as Inheritence but with interfaces.
  - Interface is shown between two diamond operators + name in italics: `<<interface>> IMyInterface`
  - Represented by **a dashed line + an empty arrow** pointing to the **implemented** interface.
  - E.g. `MotorCar ..|> Car`
- **Aggregation**:
  - A special type of association.
  - It represents a **"has-a" relationship**.
  - Objects of Class1 and Class2 have **separate lifetimes**.
  - Represented by **a solid line + an empty diamond** pointing to the aggregator class.
  - E.g. `Tortoise --o Creep`
- **Composition**
  - A special type of aggregation where parts are destroyed when the whole is destroyed.
  - It represents a **"has-a" relationship**.
  - Objects of Class1 and Class2 have the **same lifetimes**.
  - Represented by **a solid line + a filled diamond** pointing to the composite class.
  - E.g. `Heart --* Human`
- Dependency:
  - An object of one class might use an object of another class in the code of a method. If the object is **not stored in any field**, then this is modeled as a dependency relationship.
  - A special type of association.
  - Exists between two classes if **changes to the definition of one may cause changes to the other** (but not the other way around).
- Cardinality:
  - Cardinality is expressed in terms of:
    - one to one
    - one to many
    - many to many
  - E.g.:
    - `1`: ecactly one
    - `0..1`: zero to one
    - `*`: zero or more
    - `1..*`: at least one
    - `{ordered}`: ordered

#### 24. What kind of design patterns do you know? Bring at least 3 examples.

In software engineering, a design pattern is **a general reusable solution** to a commonly occurring problem in software design. It is not a finished design that can be transformed directly into code. It is **a description or template** for how to solve a problem that can be used in many different situations. Design patterns are **formalized best practices** that the programmer can use to solve common problems when designing an application or system.

Object-oriented design patterns are traditionally classified under three categories:

- **Creational**: designing how objects can be created. This often involves isolating the details of object creation so your code isn't dependent on what types of objects there are, and thus doesn't have to be changed when you add a new type of object. E.g. Factory pattern.
- **Structural**: designing objects to satisfy particular project constraints. These work with the way objects are connected with other objects to ensure that changes in the system don't require changes to those connections. E.g. **Decorator pattern**.
- **Behavioral**: designing objects that handle particular types of actions within a program. These encapsulate processes that you want to perform, such as interpreting a language, fulfilling a request, moving through a sequence (as in an iterator), or implementing an algorithm. E.g. Iterator pattern.

1. **Factory Method pattern** (creational):
   - A normal factory produces goods; a software factory produces objects. And not just that — it does so without specifying the exact class of the object to be created. To accomplish this, objects are created by calling a factory method instead of calling a constructor.
   - There's nothing wrong with using `new` to create objects but it comes with the baggage of **tightly coupling** our code to the concrete implementation class, which can occasionally be problematic.
   - **Static factory methods** returning the same type as the containing class are **substitutes for constructors**, with several advantages:
     - Unlike constructors, they have **names**. In some cases this makes our code **more readable**. More importantly, it is possible to have **two different factory methods with the same signature**.
     - Unlike constructors, they are **not required to create a new object** each time they're invoked. We can add features like pooling, caching, lazy loading, or other extras and limitations. Singleton's `getInstance()` is a good example for this.
     - Unlike constructors, they can **return an object of any subtype** of their return type.
2. **Singleton pattern** (creational):
   - The singleton pattern is used to limit creation of a class to only **one object**. This is beneficial when one (and only one) object is needed to coordinate actions across the system.
   - There are several examples of where only a single instance of a class should exist, including **caches**, **loggers**, etc.
3. **Iterator pattern** (behavioral):
   - The iterator pattern is a design pattern in which an iterator is used to **traverse a container** and access the container's elements. The iterator pattern **decouples algorithms from containers** in most cases.
   - For example, the hypothetical algorithm _SearchForElement_ can be implemented generally using a specified type of iterator rather than implementing it as a container-specific algorithm. This allows _SearchForElement_ to be used on any container that supports the required type of iterator.
   - `foreach`

#### 25. What is the purpose of the Iterator Pattern?

The purpose of the iterator pattern is to abstract away the underlying structure in which the data are kept. Data-structure can be an array, a tree, a list, etc.

Its important methods in C#:java soa

- `Current` (property)
- `MoveNext()`
- `Reset()`
- (`Dispose()`)

Uses the `yield return` keyword.

You can enumerate objects that import the `IEnumerable` interface with the `foreach` statement. It calls the `GetEnumerator()` method of the class. This `IEnumerator` then iterates through the data structure, yielding items one by one until there's no Next.

Where To Apply Iterator Pattern:

- When you want to access a collection of objects without exposing its internal representation.
- When there are multiple traversals of objects need to be supported in the collection.

#### 26. What do you know about the SOLID principles?

The SOLID principles were first conceptualized by Robert C. Martin. These design principles encourage us to create more **maintainable**, **understandable**, and **flexible** software. Consequently, as our applications **grow in size**, we can **reduce their complexity** and save ourselves a lot of headaches further down the road.

The following 5 concepts make up our SOLID principles:

1. **Single Responsibility** principle:
   - A class should only have **one responsibility**. Furthermore, it should only have **one reason to change**.
   - Benefits:
     - Testing: A class with one responsibility will have far fewer test cases
     - Lower coupling: Less functionality in a single class will have fewer dependencies
     - Organization: Smaller, well-organized classes are easier to search than monolithic ones
   - Book / BookPrinter example
2. **Open/Closed** principle:
   - _Open_ for **extension**, _Closed_ for **modification**
   - In doing so, we stop ourselves from modifying existing code and causing potential new bugs
   - Guitar example
3. **Liskov Substitution** principle:
   - If class _A_ is a subtype of class _B_, then we should be able to replace _B_ with A without disrupting the behavior of our program
   - Electric car / Motorcar example
4. **Interface Segregation** principle:
   - Larger interfaces should be split into smaller ones.
   - By doing so, we can ensure that implementing classes only need to be concerned about the methods that are of interest to them.
   - Zookeeper / BearPetter example
5. **Dependency Inversion** principle:
   - The DIP is neither dependency injection (DI) nor inversion of control (IoC). Even so, they all work great together.
   - Simply put, DI is about making software components to explicitly declare their dependencies (or collaborators) through their APIs, instead of acquiring them by themselves.
   - The principle of Dependency Inversion refers to the **decoupling** of software modules.
   - This way, instead of high-level modules depending on low-level modules, both will depend on **abstractions**.
   - With DI, the responsibility of providing the component dependencies and wiring object graphs is transferred from the components to the underlying _injection framework_.

> In traditional software development, high-level components depend on low-level ones. Thus, it's hard to reuse the high-level components. The DIP is about inverting the classic dependency between high-level and low-level components by abstracting away the interaction between them.

#### 27. How would you separate data storage code and business logic code (which uses stored data) in an application?

## Computer science

### Data Structures

#### 28. What is the difference between Stack and Queue data structure?

Queue and stack are both generic data collections.
Queues implement the so called FIFO (First-In-First-Out) method. The structure is designed to have elements be put at the end of the queue (add(e) or offer(e)) and be removed (remove() or poll()) from the beginning, much like a queue at the supermarket. The poll() and offer(e) methods can return special values in case of failure while add(e) and remove(e) throw exceptions.
Stacks implement the so called LIFO (Last-In-First-Out) method. The structure is designed much like a stack of plates on a shelf: you put the plate at the top of the stack, and take the plate from the top. Stacks offer methods for getting and removing the last item (pop()), pushing an item on the top of the stack (push(e)), taking a look at the element on the top without removing it (peek()).

#### 29. What is a graph? What are simple graphs? What are directed graphs? What are weighted graphs?

Graph is a central yet a very simple concept of mathematics: it is basically a set of vertices (a.k.a points) and a set of edges between (some of) them. In computer science vertices are usually called nodes. It is useful to know about the most important types of graphs:

- simple graph vs. multigraph / pseudograph
- undirected graph vs. directed / oriented graph
- acyclic vs. cyclic graph
- connected vs. disconnected graph

Graphs are used to model connections between entities: networks of people, places, and more abstract things like concepts or states of a machine. Directed graphs can be used to model asymmetric relations like parent/child relations or one-way transitions.

The most common type is **simple graphs** in which at most one edge (i.e., either one edge or no edges) may connect any two vertices.

**directed graphs**
If arrows may be placed on one or both endpoints of the edges of a graph to indicate directedness, the graph is said to be directed.

A **weighted graph** or labeled graph is a graph in which each branch is given a numerical weight. A weighted graph is therefore a special type of labeled graph in which the labels are numbers (which are usually taken to be positive).

#### 30. What are trees? What are binary trees? What are binary search trees?

#### 31. How can you store graphs in programs? What are the advantages/disadvantages per each?

#### 32. What are graph traversal algorithms? What is BFS, how does it work? What is DFS, how does it work?

Most of the time we want to use graph for searching a) nodes, or b) routes fulfilling some conditions, for example a) to list all nodes at distance 2 from nodeA, or b) to list the shortest routes from nodeA to nodeB. For this we need to search the graph systematically. There exist lots of algorithms to do this; the two most common strategies are called depth-first search (DFS) and breadth-first search (BFS).

`Store the root node in Container`
While (there are nodes in Container)
N = Get the "next" node from Container
Store all the children of N in Container
Do some work on N

- For depth first use a stack. (The recursive implementation uses the call-stack...)
- For breadth-first use a queue.

**Depth-first search (DFS)** is the more straightforward idea: it follows every unexplored edges until it has to turn back (when there are no unexplored edges left). To achieve this a stack data structure is needed to keep track of the path taken, consequently it can be easily implemented via recursion. While it is a good strategy to solve problems on smaller graphs (like finding the way out of a maze), in case of huge graphs the searching position will quickly drift away from the starting node, and checks nodes from the other half of the world before checking some of the neighbors of the starting node.

In the latter case a **breadth-first search (BFS)** is a better way to go. It takes closer nodes first before continuing with more distant ones; to achieve this a queue data structure is needed to add adjacent nodes to a "check later" list.

#### 33. How does dictionary work?

A dictionary is a general-purpose data structure for storing a group of objects. A dictionary has a set of keys and each key has a single associated value. When presented with a key, the dictionary will return the associated value.

A dictionary is also called a hash, a map, a hashmap in different programming languages (and an Object in JavaScript). They're all the same thing: a key-value store.

The concept of a key-value store is widely used in various computing systems, such as caches and high-performance databases.
Typically, the keys in a dictionary must be simple types (such as integers or strings) while the values can be of any type.
Keys in a dictionary must be unique; an attempt to create a duplicate key will typically overwrite the existing value for that key.

#### 34. Why is it important for keys in a hashmap to have an immutable type? (Consider string for example.)

HashMap is a data-structure where data is organized as key and values pairs. i.e. for every value there must be a key to be produced to be stored into the hashmap.

Keys are normally generated using hashcode() method.
Key’s hash code is used primarily in conjunction to its equals() method, for putting a key in map and then searching it back from map. So if hash code of key object changes after we have put a key-value pair in map, then its almost impossible to fetch the value object back from map. It is a case of memory leak. To avoid this, map keys should be immutable.

### Algorithms

#### 35. What is QuickSort? Describe the main logic of this sorting algorithm.

A searching algorithm, what it does is pick one element called the pivot and compares every element to this element, and if an element is smaller than the pivot it changes an element that is bigger this way the list is got partitioned into to part one that is biggeror equals and one thatis smaller than the pivot and makes the seame operation on thetwo parts again untill the list is eventually sorted.

## Software design

### Security

#### 36. What is OAuth2?

#### 37. What is Basic Authentication?

#### 38. What is CORS, why it’s needed in browsers?

#### 39. How can you initialize a CSRF attack?

#### 40. What is JWT used for? Where to store it on client side?

### Threaded programming

#### 41. When do you need to use threads in an application?

#### 42. What is a daemon thread?

#### 43. What is the difference between concurrent and parallel execution of code?

#### 44. What is the most important problem developers are faced when using threads?

#### 45. In what kind of situations can deadlocks occur?

#### 46. What are possible ways to prevent deadlocks from occurring?

#### 47. What does critical section or critical region mean in the context of concurrent programming?
