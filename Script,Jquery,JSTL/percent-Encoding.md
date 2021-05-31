### 퍼센트 인코딩

#### Query String 또는 Get방식으로 데이터를 넘길 때 & 또는 + 가 없어지고 공백이 나타나는 현상이 보일 때 간단하게 사용하는 인/디코딩
```
function replace(url) {
    url= url.replace(/&/g,"%26").replace(/\+/g,"%2B");
    return url;
}
```
또는
```
function replace(url) {
    url= encodeURIComponent(url);
    return url;
}
```


encodeURI( uri ) : URI에서 자주 사용하는 : ; / = ? & 등을 제외하고 인코딩하는 함수    
encodeURIComponent( uri ) : 모든 문자를 인코딩하는 함수     
decodeURI( uri ) : encodeURI의 결과물을 디코딩하는 함수     
decoudeURIComponent ( uri ) : encodeURIComponent의 결과물을 디코딩하는 함수     
