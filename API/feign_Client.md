  /// feign client Bean 중복에러    
apllication.yaml 또는 application.properties 파일에       
`spring.main.allow-bean-definition-overriding : true`     
추가

### 1. 라이브러리 사용 디펜던시 작성
#### maven 일 경우
- pom.xml에 다음과 같이 작성해줍니다.
```
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-openfeign</artifactId>
    <version>2.1.3.RELEASE</version>
</dependency>
```
#### gradle 일 경우
- build.gradle에 다음과 같이 작성해줍니다.
```
dependencyManagement {
    imports {
        mavenBom 'org.springframework.cloud:spring-cloud-dependencies:Greenwich.RELEASE'
    }
}

dependencies {
//...
    // Feign Client
    compile 'org.springframework.cloud:spring-cloud-starter-openfeign'
//...
}
```

### 2.Application.java 파일 작성
Application.java 파일에 @EnableFeignClients annotation을 작성해서 Feign Client를 사용할 것임을 알려줍니다.
```
package com.example.feignTest;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.cloud.openfeign.EnableFeignClients;

@EnableFeignClients // Feign Client를 사용할 것임을 알려줍니다.
@SpringBootApplication
public class FeignTestApplication {

	public static void main(String[] args) {
		SpringApplication.run(FeignTestApplication.class, args);
	}

}
```

컨트롤러 통해서 API 쏘자 아래는 mvc 형식으로 작성 

### 3.interface 등록
@FeignClient(name="", url="", configration=FeignTokenHeaderConfig.class)

### 4.class 등록
@Autowired
interfaceName interface;
### 5.Controller 등록
