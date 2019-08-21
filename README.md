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
java -jar target/hello-maven-1.0-SNAPSHOT.jar
```

## What is Spring?

## Spring Boot
