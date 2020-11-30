# Enterprise module (Java branch)

### Java Enterprise and Spring

#### What are the possible uses of reflection?
#### What is Spring?
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
