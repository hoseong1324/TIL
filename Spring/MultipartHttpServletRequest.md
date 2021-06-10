#### MultipartHttpServletRequest 

#### 단일,다중 파일 업로드



1. Pom.xml 설정
```
<!-- Commonfile upload  -->
  <dependency>
    <groupId>commons-fileupload</groupId>
 	  <artifactId>commons-fileupload</artifactId>
    <version>1.3</version>
  </dependency>
```

2. Servlet-context.xml 설정
```
 <beans:bean id="multipartResolver" class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
    <beans:property name="maxUploadSize" value="200000000" />
    <beans:property name="maxInMemorySize" value="200000000" />
 </beans:bean>
```

- Property type 속성 설정
 
### maxUploadSize    
#### long      
최대 업로드 가능한 바이트 크기, -1은 제한이 없음을 의미한다. 기본 값은 -1이다.     
### maxInMemorysize     
#### int    
디스크에 임시 파일을 생성하기 전에 메모리에 보관할 수 있는 최대 바이트 크기,    
기본 값은 10240 바이트이다.    
### defaultEncording     
#### String    
요청을 파싱할 때 사용할 캐릭터 인코딩, 지정하지 않은 경우 HttpServletRequest.setEncording() 메서드로 지정한 캐릭터셋이 사용된다.    
아무 값도 없을 경우 ISO-8859-1을 사용한다.   


 
3. jsp 또는 html  form 태그에 enctype="multipart/form-data 추가    
- 단일파일 업로드시
```
<form name="hoddyFileForm" action="fileUpload" method="post" enctype="multipart/form-data">
  <input type="file" name="file" />
  <input type="submit" value="전송" />
</form>
```
- 다중파일 업로드시
```
<form name="hoddyFileForm" action="fileUpload" method="post" enctype="multipart/form-data">
    <input multiple="multiple" type="file" name="file" />
    <input type="submit" value="전송" />
</form>
```

4. Controller 파람 값 설정
```
 @RequestMapping(value="hoddyFileUpload")
 public String hoddyFileUpload(multipartHttpServletRequest request){
 

      System.out.println("src value : " + src);
      
      MultipartFile multiFile = request.getFile("file");
      String path = "경로설정";
      String originFileName = multiFile.getOriginalFilename(); // 원본 파일 명
        long fileSize = multiFile.getSize(); // 파일 사이즈
        System.out.println("originFileName : " + originFileName);
        System.out.println("fileSize : " + fileSize);
        String safeFile = path + System.currentTimeMillis() + originFileName;
        try {
            multiFile.transferTo(new File(safeFile));
        } catch (IllegalStateException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        } catch (IOException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
        return "redirect:/";
 }
```
### Controller 를 설정하면서 request.getFile("file") 이부분에서 getFile()은 단일파일이며, getFiles()는 다중파일이다.


