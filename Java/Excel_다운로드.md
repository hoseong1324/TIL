### Java 엑셀로 파일 다운로드

  

* 엑셀 생성

  Workbook wb = new XSSFWorkbook();

* 시트 생성 및 시트 명 선언

  Sheet sheet = wb.createSheet("바로가게 서비스 관리");

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
	
		        // 컨텐츠 타입과 파일명 지정
		        
		 
	     
	     response.setContentType("ms-vnd/excel");
	     response.setHeader("Content-Disposition", "attachment;filename=test_"+time+".xlsx");
			        

		        // Excel File Output
		        wb.write(response.getOutputStream());
		        wb.close();

바빠서 대충 다음에 다시 정리
