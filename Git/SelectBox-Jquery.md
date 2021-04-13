```
1. 선택된 값

$("#selectboxID option:selected").val();

2. 선택된 내용

$("#selectboxID option:selected").text();

3. 선택된 위치

var index = $("#selectboxID option").index($("#selectboxID option:selected"));

4. 제일 위에 옵션 추가

$("#selectboxID").prepend("<option value='value'>Text</option>");

5. 제일 뒤에 옵션 추가

$("#selectboxID").append("<option value='value'>Text</option>");

6. 모든 옵션 바꾸기

$("#selectboxID").html("<option value='value1'>Text 1</option> <option value='value2'>Text 2</option>");

7. 특정 index 항목의 옵션 바꾸기

$("#selectboxID option:eq(indexNumber)").replaceWith("<option value='value'>Text</option>");

8. index 값으로 선택하기

$("#selectboxID option:eq(indexNumber").attr("selected", "selected");

9. text 값으로 선택하기

$("#selectboxID").val("text").attr("selected", "selected");

10. value 값으로 선택하기

$("#selectboxID").val("value");

11. index 값으로 삭제하기

$("#selectboxID option:eq(indexNumber)").remove();

12. 첫번째 항목 삭제하기

$("#selectboxID option:first").remove();

13. 마지막 항목 삭제하기

$("#selectboxID option:last").remove();

14. 선택된 옵션의 text

$("#selectboxID option:selected").text();

15. 선택된 옵션의 value

$("#selectboxID option:selected").val();

16. 선택된 옵션의 index

$("#selectboxID option").index($("#selectboxID option:selected"));

17. 옵션 항목 개수 구하기

$("#selectboxID option").size();

18. 선택된 옵션 앞의 항목 개수

$("#selectboxID option:selected").prevAll().size();

19. 선택된 옵션 뒤의 항목 개수

$("#selectboxID option:selected").nextAll.size();

20. 특정 위치 뒤에 옵션 추가

$("#selectboxID option:eq(indexNumber)").after("<option value='value'>Text</option>");

21. 특정 위치 앞에 옵션 추가

$("#selectboxID option:eq(indexNumber)").before("<option value='value'>Text</option>");

22. 모든 항목 삭제

$("#selectboxID").find("option").remove();

23. 모든 항목 삭제 후 옵션 추가하기

$("#selectboxID").find("option").remove().end().append("<option value='value'>Text</option>"); 
```
