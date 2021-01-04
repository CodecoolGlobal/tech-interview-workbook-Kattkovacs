# Enterprise module (Java branch)

### Java Enterprise and Spring

#### 1. What are the possible uses of reflection?

Java Reflection makes it possible to inspect classes, interfaces, fields and methods at runtime, without knowing the names of the classes, methods etc. at compile time.
It is also possible to instantiate new objects, invoke methods and get/set field values using reflection.

Reflection is important since it lets you write programs that do not have to "know" everything at compile time, making them more dynamic, since they can be tied together at runtime. The code can be written against known interfaces, but the actual classes to be used can be instantiated using reflection from configuration files.

Lots of modern frameworks use reflection extensively for this very reason. Most other modern languages use reflection as well, and in scripting languages (such as Python) they are even more tightly integrated, since it feels more natural within the general programming model of those languages.

#### 2. What is Spring?

The Spring Framework is an application framework and inversion of control container for the Java platform. The framework's core features can be used by any Java application, but there are extensions for building web applications on top of the Java EE (Enterprise Edition) platform. Although the framework does not impose any specific programming model, it has become popular in the Java community as an addition to the Enterprise JavaBeans (EJB) model.

#### 3. What is Spring Boot?

Spring Boot is a framework which helps create standalone Spring applications that are production-grade. It’s built on top of the Spring framework and takes an opinionated view of the Spring platform to minimize the configuration required by a typical Spring application. This makes it fast and easy to get started with.

While the Spring framework focuses on providing flexibility to you, Spring Boot aims to shorten the code length and provide you with the easiest way to develop a web application. With annotation configuration and default codes, Spring Boot shortens the time involved in developing an application.

#### 4. What is the major difference between the Standard edition (JSE) and Enterprise edition (JEE)? You can choose Spring (Spring Boot) instead of JavaEE. Focus on comparing them.

Java technology is both a programming language and a platform. The Java programming language is a high-level object-oriented language that has a particular syntax and style. A Java platform is a particular environment in which Java programming language applications run.
There are four platforms of the Java programming language:

- Java Platform, Standard Edition (Java SE)
- Java Platform, Enterprise Edition (Java EE)
- Java Platform, Micro Edition (Java ME)
- JavaFX

The Java platform (Enterprise Edition) differs from the Java Standard Edition Platform (Java SE) in that it adds libraries which provide functionality to deploy fault-tolerant, distributed, multi-tier Java software, based largely on modular components running on an application server.

#### 5. What are the advantages of the Spring Framework? Focus on the Core part.

- Lightweight - The Spring Framework is very lightweight with respect to its size and functionality. This is due to its POJO implementation, which doesn’t force it to inherit any class or implement any interfaces.

- Aspect-Oriented Programming (AOP) - This is an important part of the Spring Framework. Aspect-Oriented Programming is used for separating cross-cutting concerns (for example, logging, security, etc.) from the business logic of the application.

- Transaction Management - This is used to unify several transaction management APIs and is used to coordinate transactions for Java objects. Also, it is not tied to the J2EE environment and is used with containerless environments.

- Container - The Spring framework designs and manages the lifecycle and configurations of application objects.

- Dependency Injection - This feature of the Spring Framework allows you to develop loosely coupled applications. Therefore, the unit testing of these loosely coupled applications becomes easier. This also allows the developer to swap out some of the modules according to its need.

- Integration With Other Frameworks - A great thing about this framework is that it doesn’t try to solve the problems that have already been solved. It just tries to integrate them with its framework, which provides a solution to greater problems.

#### 6. What is a servlet? What is the purpose of DispatcherServlet in Spring?

#### 7. When do you use RestControllers, when just simple Controllers?

#### 8. What is Spring Application Context?

#### What are the main ways to define a bean in the Application Context?

#### Difference between .jar and .war files.

#### What are the major differences between Maven, Ant and Gradle?

#### What is Maven used for?

#### What does a pom.xml file contains in Maven?

### Object Relational Mapping, JPA

#### What is an ORM? What are the benefits, when to use?

Object-relational Mapping. It’s a technique to convert data between an object oriented language and a relational database, because of the non compatible data types. On one hand there are objects with fields of any kinds, and on the other hand there are databases with tables with columns of a few defined types. With the help of an ORM we define how our objects (and it’s fields) should be inserted into a database. An ORM framework helps with this (for example Hibernate).
Advantages:
• less code: data accessing is taken care of by the ORM
• no need for database knowledge: if the ORM has been setup correctly, the further development need not to worry about database issuessql
• less database load: entities are cached by the ORM, no need to query the DB for each operation
• abstraction: as we mentioned ORM takes care of data access, so your code is on a more abstract level, and you don’t need to change if you move to another database, ORM will handle the low level differences.
Disadvantages:
• performance: ORMs are made to handle many different cases which makes them complex. If performance is a very crucial factor, you should optimize for queries for your chosen mean of data storage yourself
• harder to debug
ORM is an optimal choice if your application uses mostly simple queries, and you have relatively simple objects.

#### What is the difference between JDBC and JPA? Which are the advantages and disadvantages of each? Give a general overview.

#### What is Hibernate? What are the advantages, limitations?

#### Name 3 different annotations used in JPA, what can they do for you?

#### What is object-relational impedance mismatch?

#### What is a JpaRepository? What are the 2 main methods to define queries in them?

#### Why is the Set preferred over List when we want to store OneToMany relations?

#### What kind of inheritance strategies are available? Which annotations are used to solve this?
