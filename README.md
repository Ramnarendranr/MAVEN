# Maven Project Setup and Usage Guide

## Project Setup

### Maven Project Setup

This repository contains a simple Maven project with a directory structure and configuration to build and run a Java application.

### Project Structure

- `src/main/java/hello`: Directory containing Java source files.
  - `HelloWorld.java`: Main class to run the application.
  - `Greeter.java`: Class providing a greeting message.

### Configuration Files

- `pom.xml`: Maven project configuration file.
- `JAVA_HOME`: Environment variable pointing to the Java installation directory.



## USAGE
### Create Directory:

Created a directory named maven-pro.
```
mkdir maven-pro
```

### Directory Structure:

Created the directory structure.
```
mkdir -p maven-pro/src/main/java/hello
```

<img width="359" alt="Screenshot 2024-06-04 at 8 05 24 PM" src="https://github.com/Ramnarendranr/PROJECTS/assets/122247354/bf709cf6-9d5e-4a31-981a-7474d3359022">



### Create Java Files:

Created HelloWorld.java and Greeter.java files in the hello directory.

**HelloWorld.java:**
```
package hello;

public class HelloWorld {
    public static void main(String[] args) {
        Greeter greeter = new Greeter();
        System.out.println(greeter.sayHello());
    }
}
```

**Greeter.java:**
```
package hello;

public class Greeter {
    public String sayHello() {
        return "Hello world!";
    }
}
```

### Create pom.xml:

Created a pom.xml file in the maven-pro directory.
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>org.springframework</groupId>
    <artifactId>gs-maven</artifactId>
    <packaging>jar</packaging>
    <version>0.1.0</version>

    <properties>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
    </properties>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-shade-plugin</artifactId>
                <version>3.2.4</version>
                <executions>
                    <execution>
                        <phase>package</phase>
                        <goals>
                            <goal>shade</goal>
                        </goals>
                        <configuration>
                            <transformers>
                                <transformer
                                    implementation="org.apache.maven.plugins.shade.resource.ManifestResourceTransformer">
                                    <mainClass>hello.HelloWorld</mainClass>
                                </transformer>
                            </transformers>
                        </configuration>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
</project>
```

### Set JAVA_HOME:

Added JAVA_HOME directory to the shell configuration file and sourced it.

### Compile and Package:

```
mvn compile
mvn package
```

**COMPLILE**
<img width="1113" alt="Screenshot 2024-06-04 at 8 11 46 PM" src="https://github.com/Ramnarendranr/PROJECTS/assets/122247354/12ef6e73-7b40-44c4-be3f-94eedfa6e79c">



**PACKAGE**
<img width="1469" alt="Screenshot 2024-06-04 at 8 12 07 PM" src="https://github.com/Ramnarendranr/PROJECTS/assets/122247354/1dd7263f-9c49-4c46-b061-dddfc7d5ec00">


### Run Application:
```
java -jar target/gs-maven-0.1.0.jar
```

**EXECUTABLE**
<img width="671" alt="Screenshot 2024-06-04 at 8 12 15 PM" src="https://github.com/Ramnarendranr/PROJECTS/assets/122247354/5b9cf169-05c6-4fd6-8e70-fb41d031904d">

