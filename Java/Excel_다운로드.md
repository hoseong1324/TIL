### Java 엑셀로 파일 다운로드

  
* Pom.xml 의존성 추가
```
<!-- 엑셀 -->
<dependency>
    <groupId>org.apache.poi</groupId>
    <artifactId>poi</artifactId>
    <version>4.1.2</version>
</dependency>
<dependency>
    <groupId>org.apache.poi</groupId>
    <artifactId>poi-ooxml</artifactId>
    <version>4.1.2</version>
</dependency>
```

* 엑셀 생성

 ` XSSFWorkbook wb = new XSSFWorkbook();`
  #### xls 확장자를 가진 엑셀 파일 -> HSSFWorkbook
  #### xlsx 확장자를 가진 엑셀 파일 -> XSSFWorkbook
* 시트 생성 및 시트 명 선언 

  `Sheet sheet = wb.createSheet("엑셀 테스트");`   

* 열 너비 설정
  // 셀 열 너비 설정 < 1000 이 3.55 px
		`sheet.setColumnWidth(0, 2000);`
		`sheet.setColumnWidth(1, 6000);`
* 스타일 설정   
  `CellStyle style = wb.createCellStyle();`      
  // 가는 경계선 선언       
	`cellStyle.setBorderTop(BorderStyle.THIN);`    
	`cellStyle.setBorderBottom(BorderStyle.THIN);`      
	`cellStyle.setBorderLeft(BorderStyle.THIN);  `     
	`cellStyle.setBorderRight(BorderStyle.THIN);`      
  
  // 왼쪽 정렬   
   `CellStyle leftCell = wb.createCellStyle();`   
   `leftCell.setAlignment(HorizontalAlignment.LEFT); `   
  
   // 오른쪽 정렬    
   `CellStyle leftCell = wb.createCellStyle(); `   
  ` rightCell.setAlignment(HorizontalAlignment.RIGHT);`
  
  #### cellStyle.setAlignment(HorizontalAlignment.CENTER); ( 가로)
  #### cellStyle.setVerticalAlignment(VerticalAlignment.CENTER); ( 세로 )
  // 셀에 넣어주기    
  `cell.setCellStyle(style);`    
  
  
* 폰트 설정
   // 폰트 담을 스타일 생성
   `CellStyle fontStyle = createCellStyle();`
   `Font font = wb.createFont();` 
   `cell.setCellStyle(fontStyle);`
   // 폰트크기 설정
   // 원하는 폰트크기의 X2 후 0을 붙여줍니다.
   `font.setFontHeightInPoints((short)180);`     
   `font.setFontName("맑은 고딕");`
 
* 행, 행 갯수, 열 선언
  Row row = null;

  Cell cell = null;
  int rowNum = 0;

​		    		        

		        // Header
		        row = sheet.createRow(rowNum++);
		        cell = row.createCell(0);
		        cell.setCellValue("t");
		        cell = row.createCell(1);
		        cell.setCellValue("e");
		        cell = row.createCell(2);
		        cell.setCellValue("s");
		        cell = row.createCell(3);
		        cell.setCellValue("t");
	
		        // Body
		        for (int i=0; i<3; i++) {
		            row = sheet.createRow(rowNum++);
		            cell = row.createCell(0);
		            cell.setCellValue(i);
		            cell = row.createCell(1);
		            cell.setCellValue(i+"_name");
		            cell = row.createCell(2);
		            cell.setCellValue(i+"_title");
		            cell = row.createCell(3);
		            cell.setCellValue(i+"_test");
		        }
			
			 
		        // Style
		        Style.setBorderTop(BorderStyle.THIN);
		        Style.setBorderBottom(BorderStyle.THIN);
		        Style.setBorderLeft(BorderStyle.THIN);
		        Style.setBorderRight(BorderStyle.THIN);
			
			
		        // 컨텐츠 타입과 파일명 지정
		        
		 	 // 파일 한글명 안나오는 부분 처리 
		        String excel_name = "서비스";
		        excel_name = URLEncoder.encode(excel_name,"UTF-8");
		        response.setContentType("ms-vnd/excel");
		        response.setHeader("Content-Disposition", "attachment;filename=example.xls");
		        response.setHeader("Content-Disposition", "attachment;filename="+excel_name+"_"+time+".xlsx");
	     		```

#### CellStyle에 여러가지의 스타일을 넣을 수 없기 때문에 그 상황에 맞춰서 셀 스타일에 넣어주고 표현한다.
