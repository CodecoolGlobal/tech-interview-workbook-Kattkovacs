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

- Servlets are the Java programs that runs on the Java-enabled web server or application server. They are used to handle the request obtained from the web server, process the request, produce the response, then send response back to the web server.

- In Spring MVC, all incoming requests go through a single servlet. This servlet - DispatcherServlet - is the front controller. Front controller is a typical design pattern in the web applications development. In this case, a single servlet receives all requests and transfers them to all other components of the application.

#### 7. When do you use RestControllers, when just simple Controllers?

The @RestController annotation in Spring MVC is nothing but a combination of @Controller and @ResponseBody annotation.

The job of @Controller is to create a Map of the model object and find a view but @RestController simply returns the object and object data is directly written into HTTP response as JSON or XML.

This can also be done with traditional @Controller and use @ResponseBody annotation but since this is the default behavior of RESTful Web services, Spring introduced @RestController which combined the behavior of @Controller and @ResponseBody together.

#### 8. What is Spring Application Context?

ApplicationContext is a corner stone of a Spring Boot application. It represents the Spring IoC container and is responsible for instantiating, configuring, and assembling the beans. The container gets its instructions on what objects to instantiate, configure, and assemble by reading configuration metadata.

#### 9. What are the main ways to define a bean in the Application Context?

1. **Declaring a bean in XML configuration file**
   This is the most primitive approach of creating a bean. A bean is declared in Spring’s XML configuration file. Upon startup, Spring container reads this configuration file and creates and initializes all the beans defined in this file which can be used anytime during application execution.

Here is how we define a bean in configuration XML.

<bean id="”user”" class="”com.codippa.User”"></bean>

2. **Using @Component annotation**
   @Component annotation above a class indicates that this class is a component and should be automatically detected and instantiated. Thus, a Spring component bean will look like:

```java
   package com.codippa;

@Component
public class User {
  .
}
```

3. **Using @Configuration annotation**
   This method does not require any XML file and it can be used to create a bean without XML configuration file. Create a class which you want to get as a bean, say a user and annotate it with @Configuration as:

```java
@Configuration
public class User {
  @Value("codippa")//initialize the value of this field
  private String name;
  @Value("India")
  private String country;
  public String getName() {
    return name;
  }
  public void setName(String name) {
    this.name = name;
  }
  public String getCountry() {
    return country;
  }
  public void setCountry(String country) {
    this.country = country;
  }
}
```

4. **Create an executable class having main method to test this method.**
   This class uses AnnotationConfigApplicationContext as ApplicationContext implementation to retrieve a bean from Spring context.

```java
public class Main {
   @SuppressWarnings("resource")
   public static void main(String[] args) {
      ApplicationContext context = new AnnotationConfigApplicationContext(User.class);
      User user = (User)context.getBean("user");
      System.out.println(user.getName());
      System.out.println(user.getCountry());
   }
}
```

#### 10. Difference between .jar and .war files.

**WAR**
Stands for: Web Application Resource
File extension: .war
Purpose and the way they function: WAR files are used only for web applications
Structure of the archives:WAR has a predefined structure with WEB-INF and META-INF directories
Execution: We need a server to execute a WAR

**JAR**
Stands for: Java Archive
File extension: .jar
Purpose and the way they function: JAR files allow us to package multiple files in order to use it as a library, plugin, or any kind of application
Structure of the archives: We can create a JAR with any desired structure
Execution: We can run a JAR from the command line if we build it as an executable JAR without using additional software or we can use it as a library

#### 11. What are the major differences between Maven, Ant and Gradle?

1. **Ant**
   **Pros**
   Better control over the overall build process
   Flexible enough to work with any work process
   **Cons**
   XML based build files can grow large and unmaintainable
   Lots of time and resources are necessary to maintain the build scripts
   IDE integration is difficult to achieve

2. **Maven**
   **Pros**
   Automatic dependency downloads
   All dependencies are automatically recorded in source control as part of the Maven scripts
   Standardizes and simplifies the build process
   Easily integrates with IDEs and CI/CD systems
   **Cons**
   Not flexible in creating custom workflows
   Steep learning curve and the process is difficult for novices to understand
   Time-consuming to solve build problems and new library integrations
   Not good with multiple versions of the same dependency

3. **Gradle**
   **Pros**
   Provides standardization while staying flexible
   Easy to read and write build scripts
   Better at handling multiple versions of dependencies
   Able to handle multiple programming languages and technologies
   Active community helping develop the tool
   Gradle DSL (Domain-Specific Language) makes it simple configuration structure
   Gradle provides performance improvements using incrementally, build cache and the Gradle Daemon
   **Cons**
   IDE integration not as good as Maven

#### 12. What is Maven used for?

Maven is a powerful project management tool that is based on POM (project object model). It is used for projects build, dependency and documentation. It simplifies the build process like ANT. But it is too much advanced than ANT.

In short terms we can tell maven is a tool that can be used for building and managing any Java-based project. Maven make the day-to-day work of Java developers easier and generally help with the comprehension of any Java-based project.

#### 13. What does a pom.xml file contains in Maven?

Project Object Model(POM) Files are XML file that contains information related to the project and configuration information such as dependencies, source directory, plugin, goals etc. used by Maven to build the project. When you should execute a maven command you give maven a POM file to execute the commands. Maven reads pom.xml file to accomplish its configuration and operations.

### Object Relational Mapping, JPA

#### 14. What is an ORM? What are the benefits, when to use?

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

#### 15. What is the difference between JDBC and JPA? Which are the advantages and disadvantages of each? Give a general overview.

• JDBC is a standard for Database Access
• JPA is a standard for ORM
**Pros of JDBC**

1. Clean and simple SQL processing.
2. Good performance with large data.
3. Very good for small applications.
4. Simple syntax so easy to learn.
   **Cons of JDBC**
5. Complex if it is used in large projects.
6. Large programming overhead.
7. No encapsulation.
8. Hard to implement MVC concept.
9. Query is DBMS specific

**Pros of JPA**

1. “reduces” the amount of SQL you should write to make a CRUD, simplifying those operations with some generic methods, and JPA makes the translation of the objects you send into SQL.
2. You can make “complex” operations by Criteria API, so you can handle a variety of SQL functions with objects.
   **Cons of JPA**
3. Add one more thing you have to worry about (if you have a complex database interactions).
4. JPA Have limitations, that is the reason for have a Native interface, you can send Native SQL sentences to database soooooo, you can survive without JPA or any ORM.
5. It’s heavyweight, it creates a complete environment that you almost never need.

#### 16. What is Hibernate? What are the advantages, limitations?

Hibernate is a Java framework that simplifies the development of Java application to interact with the database. It is an open source, lightweight, ORM (Object Relational Mapping) tool. Hibernate implements the specifications of JPA (Java Persistence API) for data persistence.

**Advantages**

1. ORM – maintenance is easy and cost-effective.
2. Transparent Persistence
3. Database independent
4. HQL – HQL’s advanced features like pagination and dynamic profiling are not present in SQL. So we can use it in hibernate.
5. Dual-layer Caching
6. Version Property
7. Open Source and free software
8. Scalability is easy
9. Lazy-Loading – The lazy-loading concept fetches only the necessary object that is required for the execution of an application.
10. Easy to Learn
11. Also supports collections like List, Set, Map.
12. capability to generate primary keys
13. Hibernate provided Dialect classes
14. It supports relationships like One-To-Many, One-To-One, Many-To-Many-to-Many, Many-To-One
    **Disadvantages**
15. little slower than pure JDBC
16. boilerplate code issue
17. generate many SQL statements in run time
18. Hibernate is not suitable for Batch processing
19. Hibernate is slow because it uses run time reflection
20. Lots of API to learn
21. Sometimes debugging and performance tuning becomes difficult.
22. Not suitable for Small projects
23. Does not allow multiple inserts
24. Generates complex quires with many joins
25. HQL queries cannot call PL/SQL program

#### 17. Name 3 different annotations used in JPA, what can they do for you?

**javax.persistence.Entity**: Specifies that the class is an entity. This annotation can be applied on Class, Interface of Enums.
import javax.persistence.Entity;

```java
@Entity
public class Employee implements Serializable {
}
```

**javax.persistence.Column**: Specify the column mapping using @Column annotation. Name attribute of this annotation is used for specifying the table’s column name.

```java
import javax.persistence.Column;
import javax.persistence.Entity;

@Entity
public class Employee implements Serializable {

  @Column(name = "employee_name")
  private String employeeName;
}
```

**javax.persistence.Id**: This annotation specifies the primary key of the entity.
import javax.persistence.\*;

```java
@Entity
public class Employee implements Serializable {
  @Id
  private int id;
}
```

#### 18. What is object-relational impedance mismatch?

Impedance mismatch is the term used to refer to the problems that occurs due to differences between **the database model and the programming language model**.

#### 19. What is a JpaRepository? What are the 2 main methods to define queries in them?

Spring Data repository significantly reduces the amount of boilerplate code required to implement data access layers for various persistence stores. Spring Data JpaRepository interface extends CrudRepository and provides finder methods out of the box.

2 main methods to define queries:
• **JPQL, using NamedQuery**

```java
SELECT u FROM User u WHERE u.active = TRUE
```

• **Spring QueryMethod**

```java
findByActiveTrue()
```

#### 20. Why is the Set preferred over List when we want to store OneToMany relations?

A list, if there is no index column specified, will just be handled as a bag by Hibernate (no specific ordering).

One notable difference in the handling of Hibernate is that you can't fetch two different lists in a single query. For example, if you have a Person entity having a list of contacts and a list of addresses, you won't be able to use a single query to load persons with all their contacts and all their addresses. The solution in this case is to make two queries (which avoids the cartesian product), or to use a Set instead of a List for at least one of the collections.

It's often hard to use Sets with Hibernate when you have to define equals and hashCode on the entities and don't have an immutable functional key in the entity.

#### 21. What kind of inheritance strategies are available? Which annotations are used to solve this?

• **MappedSuperclass** – the parent classes, can't be entities

@MappedSuperclass

• **Single Table** – the entities from different classes with a common ancestor are placed in a single table

@Inheritance(strategy = InheritanceType.SINGLE_TABLE)

• **Joined Table** – each class has its table and querying a subclass entity requires joining the tables

@Inheritance(strategy = InheritanceType.JOINED)

• **Table-Per-Class** – all the properties of a class, are in its table, so no join is required

@Inheritance(strategy = InheritanceType.TABLE_PER_CLASS)
