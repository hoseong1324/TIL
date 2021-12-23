 ### Pom.xml
 - Maven
  ```
        <dependency>
             <groupId>org.springframework.boot</groupId>
             <artifactId>spring-boot-devtools</artifactId>
        </dependency>
  ```
  - Gradle
  ```
  dependencies {
    developmentOnly("org.springframework.boot:spring-boot-devtools")
  }
```
 ### 2. application.yaml/properties
 
 # 자동재시작 사용여부
`spring.devtools.restart.enabled=true`      
`spring.main.allow-bean-definition-overriding: true`
