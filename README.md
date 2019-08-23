# spring101
Spring is a framework written in Java. Java projects can be built with some tools like Maven or Gradle.

## Maven
Apache Maven is a software project management and comprehension tool. Based on the concept of a project object model (POM), Maven can manage a project's build from a central piece of information. 

### Features

- simple project setup that follows best practices: Maven tries to avoid as much configuration as possible, by supplying project templates (named archetypes) (see also https://maven.apache.org/guides/introduction/introduction-to-archetypes.html)
- dependency management: it includes automatic updating, downloading and validating the compatibility
- isolation between project dependencies and plugins: with Maven, project dependencies are retrieved from the dependency repositories while any plugin’s dependencies are retrieved from the plugin repositories, resulting in fewer conflicts when plugins start to download additional dependencies
- central repository system: project dependencies can be loaded from the local file system or public repositories, such as Maven Central (www.mvnrepository.com)

### POM (Project Object Model)
POM is fundamental unit of work in Maven. It is an XML file that resides in the base directory of the project as pom.xml.
The POM contains information about the project and various configuration detail used by Maven to build the project(s) and also contains the goals and plugins. While executing a task or goal, Maven looks for the POM in the current directory. It reads the POM, gets the needed configuration information, and then executes the goal.

Example pom.xml:

```
<project xmlns = "http://maven.apache.org/POM/4.0.0"
   xmlns:xsi = "http://www.w3.org/2001/XMLSchema-instance"
   xsi:schemaLocation = "http://maven.apache.org/POM/4.0.0
   http://maven.apache.org/xsd/maven-4.0.0.xsd">
   <modelVersion>4.0.0</modelVersion>

   <groupId>com.metglobal.example</groupId> <!-- package name !-->
   <artifactId>hello-world</artifactId><!-- project name !-->
   <version>1.0</version>
</project>
```


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


### Dependencies/plugins

For running JAR file with above app, we need manifest file in it, but :

```
<build>
   <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-jar-plugin</artifactId>
        <configuration>
          <archive>
            <manifest>
              <mainClass>com.example.compass.App</mainClass>
            </manifest>
          </archive>
        </configuration>
      </plugin>
   </plugins>
</build>
```

#### Code structure
|Folder|Contains|
|-----|-----|
|src/main/java|contains java code files under the package structure|
|src/main/test|contains test codes|
|src/main/resources|contains static files and properties|

### Repositories

There are three types of repositories: local, central, remote. Remote repository syntax:
```
<repositories>
		<repository>
		    <id>jitpack.io</id>
		    <url>https://jitpack.io</url>
		</repository>
</repositories>
```

## Spring Boot
Spring Boot contains a comprehensive infrastructure support for developing a micro service and enables you to develop enterprise-ready applications that you can “just run”. Spring Boot doesn't require XML configuration, it can be easily done with annotations (**@Component**, **@Configuration**, **Service** etc.)

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
**spring-boot-starter-web** : for writing REST endpoints
**spring-boot-starter-security** : for writing security services like authentication
**spring-boot-starter-thymeleaf** : for web applications
**spring-boot-starter-actuator** : for monitoring application


### Typical project layout

![layout](https://www.tutorialspoint.com/spring_boot/images/typical_layout_of_spring_boot_application.jpg)

### Create Spring Boot project

We can create a Spring Boot project from Spring Initializr (http://start.spring.io) or from IDE (we'll use IntelliJ IDEA for this).

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

Create an object and return it as JSON instead of string.

### application.properties
properties file only consists:

```
currency.url=http://currency-test.com
```

We can access the value by: 

```
@Value("${currency.url}")
private String currencyUrl;
```

### RestTemplate for sending clients


## Thymeleaf
## JPA
