# Enterprise module (Java branch)

### Java Enterprise and Spring

#### 1. What are the possible uses of reflection?

Java Reflection makes it possible to inspect classes, interfaces, fields and methods at runtime, without knowing the names of the classes, methods etc. at compile time.
It is also possible to instantiate new objects, invoke methods and get/set field values using reflection.

Reflection can be used to get information about:

1. Class The getClass() method is used to get the name of the class to which an object belongs.
2. Constructors The getConstructors() method is used to get the public constructors of the class to which an object belongs.Math.max(0, q[i] - 2)The getMethods() method is used to get the public methods of the class to which an object belongs.
   It’s the backbone for most of the Java, J2EE frameworks.
   Some of the frameworks that use java reflection are:
3. JUnit - uses reflection to parse @Test annotation to get the test methods and then invoke it.
4. Spring - dependency injection, read more at Spring Dependency Injection
5. Tomcat - web container to forward the request to correct module by parsing their web.xml files and request URI.
6. Eclipse - auto completion of method names
7. Hibernate

#### 2. What is Spring?

Spring is the most popular application development framework for enterprise Java. The Spring Framework is an application framework and inversion of control container for the Java platform. The framework's core features can be used by any Java application, but there are extensions for building web applications on top of the Java EE (Enterprise Edition) platform. Spring framework is an open source Java platform.

#### 3. What is Spring Boot?

Spring Boot is Spring's convention-over-configuration solution for creating stand-alone, production-grade Spring-based Applications that you can "just run".[22] It is preconfigured with the Spring team's "opinionated view" of the best configuration and use of the Spring platform and third-party libraries so you can get started with minimum fuss. Most Spring Boot applications need very little Spring configuration. Features:

- Create stand-alone Spring applications
- Embed Tomcat or Jetty directly (no need to deploy WAR files)
- Provide opinionated 'starter' Project Object Models (POMs) to simplify your Maven configuration
- Automatically configure Spring whenever possible
- Provide production-ready features such as metrics, health checks and externalized configuration
  Absolutely no code generation and no requirement for XML configuration.

While the Spring framework focuses on providing flexibility to you, Spring Boot aims to shorten the code length and provide you with the easiest way to develop a web application. With annotation configuration and default codes, Spring Boot shortens the time involved in developing an application.

#### 4. What is the major difference between the Standard edition (JSE) and Enterprise edition (JEE)? You can choose Spring (Spring Boot) instead of JavaEE. Focus on comparing them.

Java technology is both a programming language and a platform. The Java programming language is a high-level object-oriented language that has a particular syntax and style. A Java platform is a particular environment in which Java programming language applications run.
There are several Java platforms. Many developers, even long-time Java programming language developers, do not understand how the different platforms relate to each other.

There are four platforms of the Java programming language:

- Java Platform, Standard Edition (Java SE)
- Java Platform, Enterprise Edition (Java EE)
- Java Platform, Micro Edition (Java ME)
- JavaFX

All Java platforms consist of a Java Virtual Machine (VM) and an application programming interface (API). The Java Virtual Machine is a program, for a particular hardware and software platform, that runs Java technology applications. An API is a collection of software components that you can use to create other software components or applications. Each Java platform provides a virtual machine and an API, and this allows applications written for that platform to run on any compatible system with all the advantages of the Java programming language: platform-independence, power, stability, ease-of-development, and security.

Java SE
When most people think of the Java programming language, they think of the Java SE API. Java SE's API provides the core functionality of the Java programming language. It defines everything from the basic types and objects of the Java programming language to high-level classes that are used for networking, security, database access, graphical user interface (GUI) development, and XML parsing.
In addition to the core API, the Java SE platform consists of a virtual machine, development tools, deployment technologies, and other class libraries and toolkits commonly used in Java technology applications.

Java EE
The Java EE platform is built on top of the Java SE platform. The Java EE platform provides an API and runtime environment for developing and running large-scale, multi-tiered, scalable, reliable, and secure network applications.
The Spring Framework is used to develop Java / Java EE applications, so it becomes part of the Java EE application but is not a Java EE technology.

#### 5. What are the advantages of the Spring Framework? Focus on the Core part.

1. Use of POJO
   Spring Framework helps the developers to develop enterprise application. It uses POJO’s which is an abbreviation for Plain Old Java Object. Using POJO for developing an application is that you don’t need an enterprise container like an application server. Also, it helps you get rid of conventional Enterprise Java Beans (EJB) by letting you can use a robust servlet container like Tomcat. This makes Spring Framework a lightweight framework.
2. Flexibility for configuring Spring
   Spring supports the use of both XML configuration as well as Java-based annotations for configuring the Spring Beans. Therefore, it provides the flexibility of using any of them for developing your enterprise application.
3. No Need Server
   As you know Spring framework provides a lightweight container. This can be activated without the use of the web server or application server.
4. Use of Spring AOP
   The Spring AOP module brings several benefits to the developer. It allows a developer to have different compilation unit or separate class loader. Along with that, it uses IoC for dependency injection which allows aspects to be configured normally.
   Follow this link to know about Spring LoC Containers in detail.
5. No Need to Reinvent
   One of the major benefits of Spring Framework for development of enterprise application is that you can leverage from Spring. Spring uses technologies such as JDK timers, ORM frameworks, Java EE etc. So that developers need not have to learn all those technologies or frameworks in order to develop applications.
6. Use of Modularity
   The Spring Framework provides modularity to the developers. It helps them to choose which packages or classes can be used or ignored. With tons of classes and packages, it comes as a boon to developers to identify and choose the packages or classes without any problems.
7. Ease of Testability
   One the feature of Spring Dependency injection helps in gearing up testability. It simplifies the injection of test data with the use of JavaBean POJO.
8. The Consistency of Transaction Management
   Spring Framework can easily scale up or down the local as well as global transactions using JTA. It is due to consistent transaction management interface.
   Read More about Spring Transaction Management
9. Well- Designed Web Framework
   Spring has well designed MVC framework which provides a great alternative solution to a legacy web framework. You will learn about Spring MVC Framework integration later in the coming articles.
10. Inversion Control and API’s
    Spring Framework provides inversion control and APIs to translate exceptions thrown by JDBC, Hibernate into unchecked and consistent ones.

#### 6. What is a servlet? What is the purpose of DispatcherServlet in Spring?

#### When do you use RestControllers, when just simple Controllers?

#### What is Spring Application Context?

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
