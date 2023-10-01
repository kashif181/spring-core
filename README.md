
# Spring Core Fundamentals 

## Inversion of Control
Is basically a object-oriented Principle, in which an object do not know the concrete implementations of other objects but have an abstract (Interface) knowledge 

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

## Dependency Injection (DI)
In Dependency Injection their is primarily a one independent object that require many other dependent objects, so these dependent objects are provided/transferred to it on the time of creation.
There are may ways of tranferring dependent object few are via constructor or setters
 * **Few advantages of DI:**
    -  Loosly coupled
    -  Dependency resolution at runtime
  * **DI Components:**
    -  Service,
    -  Consumer
    -  Injector

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

# Spring IOC Container
Basically a machanisum through which a losely coupled application is designe using IOC and DI principle of Spring
  * **Context/Container:** Where all beans resides in Spring and managed
    *  AnnotationConfigApplicationContext
    *  ClassPathXMLApplicationContext
    *  FileSystemXMLApplicationContext
    *  AnnotationConfigWebApplicationContext
    *  XMLWebApplicationContext
  *  **Bean:** Any POJO/Java Bean Resides in IOC container With following scope singelton(Default), prototype, request, session, global-session
  *  **Bean Auto Wiring:** There are different way of autowiring like constructor based, setter based, by type and by name
   ~~~
    // using autowird annotation on type
@Autowired
private Employee employee
~~~
~~~
// constructor is used for autowire by constructor
public EmployeeService(Employee emp) {
  System.out.println("Autowiring by constructor used");
  this.employee = emp;
}
~~~
~~~
//used for autowire byName and byType
public void setEmployee(Employee emp) {
  this.employee = emp;
}
~~~
~~~
//setter based
@Autowired
public void setEmployee(Employee emp) {
  this.employee = emp;
}
~~~
  * **Bean Life Cycle:**
    * Instantiation (Constructor Call), Populate Properties and Dependencies (Injection), Initialization (If InitializingBean is implemented than afterPropertiesSet()), Bean Ready for Use, destroy (if DisposableBean interface impelmented)
    * @PostConstruct, @PreDestroy annotation can be used instead of implementing InitializingBean, DisposableBean interfaces
     
# Spring AOP Fundamentals 
  * **Aspect:** Its a concern that cut (effect) across multiple part/classes of application **@Aspect**
  * **Join Point:** Specific point/location in the application (while executing)
  * **Advice:** An action that need to taken at Join point
    * @Before: Before Join Pont
    * @After: After Join Pont
    * @AfterReturning: After Normal Execution
    * @AfterThrowing: In case of throwing exception
    * @Around: Intercepts and can modify Join Point Execution
  * **Point Cut:** A rule/condition that need to be matched so that advice need to be taken for Join Point
    * @Before(**"execution(public String getName())"**)
  * **Target/Adviced Object:** An object on which advices are applied, always a proxy object
  * **AOP proxy:** an object created by the AOP framework in order to implement the aspect contracts
  * **Weaving:** Linking aspects with other objects to create the advised proxy objects
  * **aspectjrt and aspectjweaver**

# Spring Core Annotation
* @Configuration: (C) With it Declares one or more @Bean methods, classes are processed by the Spring container to generate bean definitions and service requests for those beans at runtime
* @ComponentScan(basePackages = {},basePackageClasses = {},includeFilters = {},excludeFilters = {},useDefaultFilters = true/false) (C)
* @Component: (C) Indicates that an annotated class is a “component” 
	* @Service
	* @Repository
* @Bean(name = "comp", initMethod = "turnOn", destroyMethod = "turnOff"): (M) Produces a bean to be managed by the Spring container
	* @Primary: To indicate the primary bean to be used when there are multiple beans of the same type
	* @Qualifier: To specify the exact bean to be injected when there are multiple candidates of the same type
	* @PreDestroy and @PostConstruct: are alternative way for bean initMethod and destroyMethod
	* @Scope(value="request"): (C) define the scope of Bean
* @Autowired(required=false): (C, F, M) For automatic dependency injection
* @PropertySource: (C) For adding a property source to Spring’s Environment
* @Value: (C, F, M) Used to assign default values to variables and method arguments 


  
