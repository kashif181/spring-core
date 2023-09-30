
# Spring Core Fundamentals 

## Inversion of Control
Is basically a object-oriented Principle, in which and and object do not depend on concrete implementations of other objects but have an abstract (Interface) knowledge 

```
public class MyApplication {
  EmailMessageService emailMessageService = new EmailMessageService()
}
```
```
@Component
public class MyApplication {
  @Autowired
  private MessageService messageService;
}
```

## Dependency Injection
In Dependency Injection their is primarily a one independent object require many other dependent objects, so these objects are provided/transferred to it on the time of creation.
There are may ways of tranferring via constructor or setters
  * **Loosly coupled** 
  * **Dependency resolution at runtime**
  * **DI Components:** Service, Consumer and Injector

## Aspect Oriented Programing
Basically a Programing paradigm in which as aspect (part) that affect multiple parts of the application/code are typically separate from the core business logic commmon example is logging, security and error handling e.t.c

## Spring Framework Ecosystem

  ### Spring Framework core Components
  Followin are core Components of spring Framework
  * **Spring Expression Language (SEpL):** for manipulating object graph at runtime (its internal implementation)
  * **Context:** Basically a container of bean mainly of two type Bean Factory (Basic Spring Context) and Application Context
  * **Core module:** Basically IOC and Dependency Injection
  * **Bean:** Responsible for creating and managing Beans

  ### Spring Web Components
  * **Spring Web:** 
  * **Spring MVC:** MVC implementation
  * **Spring Web Socket:** For communication over web sockets
  * **Spring Web Portlet:** For handling java portlet technology

  ### Spring DATA
  * **Spring JDBC:** Spring implementaion of JDBC few lines of codes as compare to conventional JDBC (JdbcTemplate) 
  * **Spring JPA:** ORM
  * **Spring OXM:** Object / XML / JAXB
  * **Spring JMS:** For Messaging
  * **Spring Transaction:**
  * **Spring Caching:**

  ### Spring Miscellaneous Modules
  * **Spring AOP:** AspectJ
  * **Spring Test:**
  


  
