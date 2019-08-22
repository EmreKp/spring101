# spring101
Spring is a framework written in Java. Java projects can be built with some tools like Maven or Gradle. We will first look into Maven, then definition of Spring and Spring Boot. 

## Maven
Apache Maven is a software project management and comprehension tool. Based on the concept of a project object model (POM), Maven can manage a project's build from a central piece of information. 

### POM (Project Object Model)
POM is fundamental unit of work in Maven. It is an XML file that resides in the base directory of the project as pom.xml.
The POM contains information about the project and various configuration detail used by Maven to build the project(s) and also contains the goals and plugins. While executing a task or goal, Maven looks for the POM in the current directory. It reads the POM, gets the needed configuration information, and then executes the goal. DEVAM EDEBİLİRSİN

```
<project xmlns = "http://maven.apache.org/POM/4.0.0"
   xmlns:xsi = "http://www.w3.org/2001/XMLSchema-instance"
   xsi:schemaLocation = "http://maven.apache.org/POM/4.0.0
   http://maven.apache.org/xsd/maven-4.0.0.xsd">
   <modelVersion>4.0.0</modelVersion>

   <groupId>com.metglobal.example</groupId>
   <artifactId>hello-world</artifactId>
   <version>1.0</version>
</project>
```

### Features

- simple project setup that follows best practices: Maven tries to avoid as much configuration as possible, by supplying project templates (named archetypes)
- dependency management: it includes automatic updating, downloading and validating the compatibility, as well as reporting the dependency closures (known also as transitive dependencies)
- isolation between project dependencies and plugins: with Maven, project dependencies are retrieved from the dependency repositories while any plugin’s dependencies are retrieved from the plugin repositories, resulting in fewer conflicts when plugins start to download additional dependencies
- central repository system: project dependencies can be loaded from the local file system or public repositories, such as Maven Central (www.mvnrepository.com)

### Create and build Maven project

Creating:

```
mvn archetype:generate -DgroupId=com.metglobal.example -DartifactId=hello-world -DarchetypeArtifactId=maven-archetype-quickstart 
``` 

Packaging:  `mvn package` | `mvn install` | `mvn clean package` | `mvn clean install (preferred)`

Running:

```
cd target/classes
java com.metglobal.example.App
```

### Dependencies
Maven does the dependency management using the concept of Repositories. 
üstteki için manifest bağımlılığı ekleyip örnekle ve java jarla tekrar çalıştır

### Repositories
buna bakarsın

### Snapshot

## Spring Framework
Spring is a MVC framework written in Java. It also supports Kotlin and Groovy languages.

### Spring Boot
Spring Boot contains a comprehensive infrastructure support for developing a micro service and enables you to develop enterprise-ready applications that you can “just run”. It contains of Spring MVC, Tomcat 

### Starter dependencies
Parent pom is required for all Spring Boot applications:

```
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.1.6.RELEASE</version> <!-- this is Spring Boot version !-->
    <relativePath />
</parent>
```

Most used starter dependencies:


### Typical project layout



### Create Spring Boot project

We can create a Spring Boot project by three ways:

1. From command line
2. From Spring Initializr (http://start.spring.io)
3. From IDE (we'll use IntelliJ IDEA for this)


## Create REST service

We should add `spring-boot-starter-web` dependency for creating REST APIs.

```
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

### Controller

We should specify controllers with @Controller or @RestController annotations. Example controller:

```
@RestController
public class MainController {
    @RequestMapping(value = "/", method = RequestMethod.GET) // or @GetMapping
    public String hello() {
        return "Hello world";
    }
}
```

### Returning objects

## Bundan sonra controller metodunu servise taşı ve autowiringi öyle göster

### application.properties


### RestTemplate for sending clients

Döviz servisine bağlan

## Thymeleaf
## JPA (sarkabilir)

