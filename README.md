# spring-boot-demo

In this repo you'll find insturctions to create a simple spring boot web application via vscode on mac.

# Requirments
1. Install VSCode - https://code.visualstudio.com/download
2. Install vscode extension - Spring Initializr Java Support - https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-spring-initializr
3. Install vscode extension - Spring Boot Tools - https://marketplace.visualstudio.com/items?itemName=Pivotal.vscode-spring-boot
4. Install vscode extension - Spring Boot Dashboard - https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-spring-boot-dashboard
5. Install vscode extension - Java Extension Pack - https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack


# Start
1. Open empty vscode (on empty directory)
2. cmd + shift + p -> Spring Initializer -> Create a maven project
3. spring boot version -> 2.3.3
4. project langauage -> java
5. group id -> com.example
6. artifact id -> demo
7. packaing type -> jar
8. java version -> 11
9. dependecies -> Spring web, Spring Boot DevTools, Lombok
10. Generate into this folder -> Open
11. if question pops up - truest maven -> Yes
12. Go to pom.xml file
13. Right click on the file -> Add starters - ensure all dependecies exists
14. Go to DemoApplication.java file
15. Add new file next to it (in the same directory) called - HelloController.java - this is the code

```
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class HelloController {

    @RequestMapping("/")
    public String index(){
        return "Demo Hello World";
    }
    
}
```
16. Run the application using Func + F5 (or Run & Debug)
17. The application should be launched
18. Navigate to http://localhost:8080 , you should see "Demo Hello World"
19. go to the root dir of the new application and run ```./mvnw package -DskipTests``` to build the jar (ignore tests folder)
20. go to the root dir of the new application and run ```java -jar target/demo-0.0.1-SNAPSHOT.jar```
21. the application should run and you should be able to browse to it via http://localhost:8080
22. if you get a java error: UnsupportedClassVersionError: com/example/demo/DemoApplication has been compiled by a more recent version of the Java Runtime, then, you should run ```echo $JAVA_HOME```
23. this should return the path to the java installation, usually: /Library/Java/JavaVirtualMachines/jdk1.8.0_241.jdk/Contents/Home
24. If this is not the java version (in our case we need java 11) then 
25. run the command: ```export JAVA_HOME=/Library/Java/JavaVirtualMachines/adoptopenjdk-11.jdk/Contents/Home```
26. this will tell java to run version 11
27. to ensure that, run ```java -version``` and ensure you get "openjdk version "11.0.8" 2020-07-14"
28. Now, re-run ```java -jar target/demo-0.0.1-SNAPSHOT.jar```
29. The jar should be app and running and the application is launched on port 8080


