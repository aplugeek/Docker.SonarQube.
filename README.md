# Docker.SonarQube
Docker快速构建代码分析工具

1) 配置Maven的settings.xml

[html] view plain copy

- <settings>
-     <pluginGroups>
-         <pluginGroup>org.sonarsource.scanner.maven</pluginGroup>
-     </pluginGroups>
-     <profiles>
-         <profile>
-             <id>sonar</id>
-             <activation>
-                 <activeByDefault>true</activeByDefault>
-             </activation>
-             <properties>
-                 <!-- Optional URL to server. Default value is http://localhost:9000 -->
-                 <sonar.host.url>
-                   http://myserver:9000
-                 </sonar.host.url>
-             </properties>
-         </profile>
-      </profiles>
- </settings>

2) 配置Maven项目的pom.xml文件

[html] view plain copy

-   <properties>
-     <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
-     <sonar.language>java</sonar.language>
-   </properties>
-   <build>
-   <pluginManagement>
-     <plugins>
-       <plugin>
-         <groupId>org.sonarsource.scanner.maven</groupId>
-         <artifactId>sonar-maven-plugin</artifactId>
-         <version>3.1.1</version>
-       </plugin>
-     </plugins>
-   </pluginManagement>
- </build>

3) 使用maven-sonar-plugin插件以进行SonarQube分析

mvn clean verify sonar:sonar

或mvn clean install org.sonarsource.scanner.maven:sonar-maven-plugin:3.1.1:sonar


https://hub.docker.com/_/sonarqube/