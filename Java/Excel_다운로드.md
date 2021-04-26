### Java 엑셀로 파일 다운로드

  

* 엑셀 생성

 ` XSSFWorkbook wb = new XSSFWorkbook();`
  
* 시트 생성 및 시트 명 선언 

  `Sheet sheet = wb.createSheet("엑셀 테스트");`   

* 스타일 설정   
  CellStyle style = wb.createCellStyle();      
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
		        Style.setBorderTop(BorderStyle.THICK);
		        Style.setBorderBottom(BorderStyle.THICK);
		        Style.setBorderLeft(BorderStyle.THICK);
		        Style.setBorderRight(BorderStyle.THICK);
			
			
		        // 컨텐츠 타입과 파일명 지정
		        
		 	 // 파일 한글명 안나오는 부분 처리 
		        String excel_name = "서비스";
		        excel_name = URLEncoder.encode(excel_name,"UTF-8");
		        response.setContentType("ms-vnd/excel");
		        response.setHeader("Content-Disposition", "attachment;filename=example.xls");
		        response.setHeader("Content-Disposition", "attachment;filename="+excel_name+"_"+time+".xlsx");
	     		```

#### 바빠서 대충 다음에 다시 정리
#### 
