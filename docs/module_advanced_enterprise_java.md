# Enterprise module (Java branch)

### Java Enterprise and Spring

#### What are the possible uses of reflection?

Java Reflection makes it possible to inspect classes, interfaces, fields and methods at runtime, without knowing the names of the classes, methods etc. at compile time.
It is also possible to instantiate new objects, invoke methods and get/set field values using reflection.

Reflection can be used to get information about: 1. Class The getClass() method is used to get the name of the class to which an object belongs. 2. Constructors The getConstructors() method is used to get the public constructors of the class to which an object belongs.Math.max(0, q[i] - 2)The getMethods() method is used to get the public methods of the class to which an object belongs.
It’s the backbone for most of the Java, J2EE frameworks.
Some of the frameworks that use java reflection are: 1. JUnit - uses reflection to parse @Test annotation to get the test methods and then invoke it. 2. Spring - dependency injection, read more at Spring Dependency Injection 3. Tomcat - web container to forward the request to correct module by parsing their web.xml files and request URI. 4. Eclipse - auto completion of method names 5. Hibernate

#### What is Spring?

Spring is the most popular application development framework for enterprise Java. The Spring Framework is an application framework and inversion of control container for the Java platform. The framework's core features can be used by any Java application, but there are extensions for building web applications on top of the Java EE (Enterprise Edition) platform. Spring framework is an open source Java platform.

#### What is Spring Boot?

#### What is the major difference between the Standard edition (JSE) and Enterprise edition (JEE)? You can choose Spring (Spring Boot) instead of JavaEE. Focus on comparing them.

#### What are the advantages of the Spring Framework? Focus on the Core part.

#### What is a servlet? What is the purpose of DispatcherServlet in Spring?

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
