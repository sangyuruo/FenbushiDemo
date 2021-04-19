springboot 开发第一个应用

1.  Creating the POM
编写pom.xml : 


<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<groupId>com.example</groupId>
	<artifactId>myproject</artifactId>
	<version>0.0.1-SNAPSHOT</version>

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.1.7.RELEASE</version>
	</parent>

	<!-- Additional lines to be added here... -->

</project>




2. Adding Classpath Dependencies
输入 mvn dependency:tree 查看依赖树, 此时依赖树为空。
增加依赖
<dependencies>
	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-web</artifactId>
	</dependency>
</dependencies>

再输入 mvn dependency:tree ，会看到依赖树中有 springboot 以及 tomcat 等。

3. Writing the Code
编写类  src/main/java/Example.java:  

import org.springframework.boot.*;
import org.springframework.boot.autoconfigure.*;
import org.springframework.web.bind.annotation.*;

@RestController
@EnableAutoConfiguration
public class Example {

	@RequestMapping("/")
	String home() {
		return "Hello World!";
	}

	public static void main(String[] args) {
		SpringApplication.run(Example.class, args);
	}

}



4. Running the Example
mvn spring-boot:run



5. Creating an Executable Jar
增加插件配置到 pom.xml 中 ：
<build>
	<plugins>
		<plugin>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-maven-plugin</artifactId>
		</plugin>
	</plugins>
</build>


mvn package

查看jar 包内内容： 
jar tvf target/myproject-0.0.1-SNAPSHOT.jar

执行：
java -jar  target/myproject-0.0.1-SNAPSHOT.jar
