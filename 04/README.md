# 폼 관련 태그들.       
특정 항목에 사용자가 입력하는 형태.  
폼과 관련된 대부분의 작업은 DB기반 -> 폼의 형태는 HTML, 정보 처리는 ASP, PHP, JSP 같은 서버프로그래밍을 이용.              
## 폼 만들기            
```<form>```            
+ 폼을 만드는 기본적 태그.          
+ 여러 폼 요소를 삽입. 
### form 태그의 속성        
+ **method** : 사용자가 입력한 내용들을 서버쪽에 전달하는 방식 지정.      
 + **get** : 주소 표시줄에 입력 내용이 그대로 전달.         
 + **post** : 사용자의 입력을 표준입력으로 전달. 대부분 이 방식.        
+ **name** : 폼의 이름을 지정. 폼들을 구분하기 위해 사용됨.         
+ **action** : form태그 안에 내용들을 처리해줄 서버 상 프로그램 지정.   
+ **target** : action 태그(?)에서 지정한 스크립트 파일을 현재 창이 아닌 다른 위체에 열도록 지정.    
+ **autocomplete** : 자동완성기능. 사용자가 입력한 내용을 기억했다가 보여주는 기능.         
--------------------------------------------------------        
```<input>```       
+ 사용자가 내용을 입력하는 필드를 삽입하거나 버튼을 삽입할 때.    
 + **type** : 버튼, text, 비밀번호 등 어떤 형식으로 입력 받을지 정함. 
--------------------------------------------------------    
```<label>```       
+ 폼 요소에 레이블을 붙이기 위한 것. 창 옆에 붙은 텍스트.       
```
<label for = "name1">
    <input id = "name1" ... >
</label>
```     
+ **id** 속성을 이용해 서로 연걸하기 때문에 꼭 **label**태그 안에 넣지 않아도 됨.   
+ 이 label태그를 이용해 체크박스에서 텍스트를 눌러도 체크박스가 선택되게 만들 수 있다.      
```
<form>
    <h3>label태그를 사용하지 않을 때.<h3>
    <ul>
        <li> <input type="checkbox", value="test1">1번</li>
        <li> <input type="checkbox", value="test2">2번</li>
    </ul>

    <h3>label태그를 사용할 때.<h3>
    <ul>
        <li> 
            <label><input type="checkbox", value="test1">1번</label>
        </li>
        <li> 
            <label><input type="checkbox", value="test2">2번</label>
        </li>
    </ul>
</form>
```         
-------------------------------------------------------
```<fieldset>, <legend>```      
+ 하나의 폼 안에서 여러 구역을 나눌 때 사용하는 태그.       
```
<form>
    <fieldset>
        <legend>제목1</legend>
        ...
    </fielcset>
    <fieldset>
        <legend>제목1</legend>
        ...
    </fielcset>
</form>
```         
## 사용자 입력을 위한 input태그     
+ 폼에서 사용자 입력을 받기 위해 사용하는 태그.     
```<input type="유형" [속성 = "속성값"]>```           
+ 웹에서의 폼은 크게 사용자가 입력하는 부분과 입력내용을 서버로 보내는 버튼부분으로 나눌수 있다.        
이때 사용자가 입력하는 부분을 만들 때 사용되는 태그.        
체크박스나 버튼도 input태그를 이용.         
### id 속성 사용하기        
폼을 만들다 보면 똑같은 폼 요소가 반복적으로 사용됨.    
-> 여러개의 폼 요소를 구분하기 위해 사용되는 속성.      
```<input type = "text" id = "user-name">```        
+ id속성값의 조건
 + 최소 한 개 이상의 문자.      
 + 공백 사용 불가.  
->**label**태그를 이용해 캡션을 붙일 수도 있고 **CSS**를 이용해 다른 형태로 꾸밀수 있음.      
### type 속성
+ input태그에서 입력형태를 지정할 때 사용되는 속성.     
유형이 많지만 다 사용되기 때문에 꼭 알아야 함! 이름과 연관지어 기억.    
+ type 속성의 유형값.       
 + **hidden** : 사용자에 보이지 않지만 서버로 넘겨지는 값.      
 + **text** : 한줄 짜리 텍스트 박스.    
 + **search** : 검색상자.   
 + **tel** : 전화번호 입력 필드.    
 + **url** : URL주소 입력 필드.     
 + **email** : 메일 주소 입력 필드.     
 + **password** : 비밀번호 입력 필드.       
 + **datetime** : 표준시로 설정된 날짜+시간(분할 초까지) 입력필드.      
 + **datetime-local** : 사용자가 있는 지역 날짜+시간 입력필드.      
 + **date** : 사용자 지역 기준 날짜(y-m-d).
 + **month** : 사용자 지역 기준 날짜(y-m).
 + **week** : 사용자 지역 기준 날짜(y-w).       
 + **time** : 사용자 지역 기준 시간(h-m-s-ms).          
 + **number** : 숫자를 조절할 수 있는 화살표.       
 + **range** : 숫자를 조절할 수 있는 슬라이드 바.       
 + **color** : 색상 표.         
 + **checkbox** : 2개 이상 선택 가능한 체크박스.        
 + **radio** : 1개만 선택 가능한 라디오버튼.        
 + **file** : 파일을 첨부할 수 있는 **버튼**    
 + **submit** : 서버 전송 버튼
 + **image** : submit버튼 대신 사용할 이미지.       
 + **reset** : 리셋 버튼.       
 + **button** : 버튼.       
-> 브라우저 마다 지원이 다르기 때문에 확인 : (caniuse)[http://caniuse.com/ciu/index]
#### type="hidden"      
```<input type="hidden" name="name1" value="Data1">```      
+ name 속성으로 필드의 이름을 정하고, value의 값을 서버에 전달.         
#### type="text"        
```<input type="text" name="name1" size="10" value="input." maxlength = "10">```          
+ size속성은 텍스트 필드의 글자 표시 길이 제한.      
+ value속성은 텍스트 필드 부분에 표시될 내용.       
+ maxlength속성은 텍스트 필드의 문자 개수 제한.         
#### type="password"        
```<input type="password" name="name1" size="12" maxlength="10">```       
+ 사용자가 입력한 내용들이 화면에 보이지 않음.      
+ value속성이 없다는 것 제외하고 text와 같다.       
#### type="search", "url", "email", "tel"-분화된 텍스트필드.     
+ 정보에 맞게 분화된 텍스트 필드 속성.      
+ **type="search"**     
 + 검색 상자 필드. 보통 submit와 같이 사용한다.         
 ```
 <input type="search">
 <input type="submit" value="검색">
 ```
+ **type="url"**        
 + 웹 주소 필드. 공백x, http://로 시작해야 함.      
 + 텍스트 필드 기반이라 text와 사용속성이 같다.     
 ```<input type="url" ...>```       
+ **type="email"**       
 + 기존에는 JS로 @문자를 체크하는 과정이 필요했었지만,      
  이 속성으로 브라우저 자체에서 자동으로 체크.      
 + 텍스트 필드 기반이라 text와 사용속성이 같다.         
 ```<input type="email" ... >```            
+ **type="tel"**        
 + 전화번호 필드. 이 값으로 바로 전화걸기 O. 
 + 텍스트 필드 기반이라 text와 사용속성이 같다.    
 ```<input type="tel" ... >```      
#### type="number"        
 + 사용자가 입력한 내용을 숫자로 인식. 스핀박스가 뜰 때도 있음.     
 ```<input type="number" min="1" max="5" step = "2" value="1">```      
 + min 속성은 입력가능한 최솟값, max 속성은 입력가능한 최댓값 지정.     
 + step 속성은 숫자 간격 지정. 디폴트는 1. 생략 가능.       
 + value 속성은 초깃값. 
#### type="range"       
 + 슬라이드 막대를 움직여 숫자값 입력. 
 + 속성 값은 number필드와 같다.     
 ```<input type="range" .. >```     
#### type="radio" , type="checkbox"        
 + 여러 항목 중 원하는 항목을 선택하는 태그. 
 + 한 개 or 여러개의 차이. 
 ```
 <input type = "radio" name = "name1" value="data1" checked=1>
 <input type = "radio" name = "name1" value="data2" >
 ...
 ```   
 + name속성은 폼 안에서 항목을 구분하는 용도. radio는 한개만 선택가능한 경우라서 name이름을 동일하게 설정.      
 + value 속성은 서버에 전달하는 값. 필수속성. 
 + checked 속성은 기본으로 선택하고 싶을 때 사용.       
#### type="color"       
 + 색상 선택 상자. 색상값은 16진수로만 가능하다.        
 + value 속성은 기본값이다.     
 ```<input type="color" value="#00FF00">```     
#### type="date", "month", "week"        
 + 날짜를 표시하는 태그. 
 + value 속성으로 기본값 지정. 
 + date:yyyy-mm-dd / month:yyyy-mm / week:yyyy-W24      
 + 위 태그는 달력이 표시가 되고 달력에서 날짜를 선택할수도 있음.        
  -> 크롬 한정.         
#### type="time","datetime", "datetime-local"       
 + 날짜, 시간 지정 태그. 
 ```<input type="time" ... >```         
 + min 속성 : 날짜, 시간의 최솟값 지정.     
 + max : 날짜, 시간의 최댓값 지정.      
 + step : 스핀박스의 증가/감소 값 지정.     
 + value : 화면에 표시할 초기값 지정.       
#### type="submit", "reset"         
 + reset 태그는 input요소에 입력된 모든 정보를 재설정.      
 + submit 태그는 사용자가 폼에 입력한 정보를 form태그에서 지정한 폼 처리 프로그램에 넘겨짐.         
 ```<input type="submit" value="버튼내용" .. >```           
#### type="image"       
 + submit 버튼대신 전송 이미지를 넣는다. 즉 버튼을 사진으로 바꿈.       
 ```<input type="image" src="./1.jpg" alt="1" ...>```       
#### type="button"        
 + 폼 안에 버튼형태를 만듬. 
 + submit, reset처럼 자체 기능은 없고 스크립트 함수 등을 연결해 사용.   
 ```<input type="button" value="내용">```       
#### type="file"         
 + 파일 첨부 기능 버튼. 
 ```<label>첨부파일<input type="file"></label>```       
------------------------------------------------------------        
## input 태그의 다양한 속성         
### autofocus 속성       
```<input type="text" id="name1" autofocus>```         
+ 폼의 요소 중 원하는 요소에 마우스 커서를 표시하는 것. 
### placeholder 속성 - 자주쓴다.        
```<input type="text" id="uid" plascholder="뭐없이입력">```     
+ 해당 필드에 어떤 내용을 입력해야 할지 알려줌.     
+ 필드를 클릭하면 사라짐.   
### readonly 속성       
```<input type="text" value="블라블라" id='id1' readonly="true">```      
+ 해당 필드를 읽기 전용으로 바꿈.       
### required 속성       
```<input type = "text" .. required> ```    
+ 필수적으로 입력해야 하는 필드를 지정하는 태그.    
 입력하지 않으면 브라우저에서 오류코드 제공.    
### max, min, step 속성         
+ max와 min은 각각 최댓값, 최솟값이며 step은 숫자의 간격을 지정.        
+ input 태그의 유형이 date, datetime, datetime-local, month, week, time, number, range일때만 사용가능.      
### size, minlength, maxlength 속성         
+ 텍스트 길이의 조건.       
+ size는 화면에 보여줄 텍스트의 길이를 제한.    
+ minlength와 maxlength는 입력 가능한 텍스트의 길이를 제한.     

이 밖에도 많은 속성들이 있다. 
-----------------------------------------------------------------     
## 여러 데이터 나열해 보여주기.     
+ 여러 데이터들을 나열하고 사용자가 선택하게끔 하는 태그들.         
### <select>, <optgroup>, <option> 태그         
+ 사용자가 내용을 입력하는 것이 아닌 여러 옵션 중 선택하게끔 할 때 드롭다운 목록을 사용한다.      
```
<select 속성="속성값">
    <option value="data" [속성="속성값"]>내용1</option>
    <option value="data" [속성="속성값"]>내용2</option>
    <option value="data" [속성="속성값"]>내용3</option>
</select>
```         
+ 만약 서버로 정보를 보낼 때 value 안 값이 전달.        
#### select 태그의 속성.        
+ size : 화면에 표시할 드롭다운 매뉴의 항목 수.         
+ multple : 브라우저 화면에 여러 개의 옵션이 함께 표시. **ctrl**키를 누른 상태로 드롭다운 매뉴에서 여러개 선택 가능.        
#### option 태그의 속성         
+ value : 선택되었을 때 서버로 넘겨질 값.       
+ selected : 기본으로 선택되어 있는 옵션.       

만약 드롭다운 항목에서 몇 가지 그룹으로 묶어야 할 경우. 
**optgroup** 태그를 사용한다.       
label이라는 속성으로 그릅의 이름을 지정할 수 있다.      
```
<select 속성="속성값">
  <optgroup label = "내용">
    <option value="data" [속성="속성값"]>내용1</option>
    <option value="data" [속성="속성값"]>내용2</option>
    <option value="data" [속성="속성값"]>내용3</option>
  </optgroup>
</select>
```
### datalist, option 태그       
+ 데이터 목록 중에서 값을 선택하도록 함. 텍스트 필드에 값을 직접 입력하는 것이 아님.    
+ 보통 input태그를 함께 사용. input태그의 **list**속성값과 **id**를 같게 한다.    
```
<input type="text list="id1">
<datalist id="id1">
    <option value = "data1" label="데이터1">내용1</option>
    <option value = "data2" label="데이터2">내용2</option>
    ...
</datalist>
```         
#### option 태그의 속성         
+ value : 선택되었을 때 서버로 넘겨질 값.       
+ label : 사용자를 위해 브라우저에 표시할 값. 지정하지 않으면 value값을 레이블로 사용.      

### textarea 태그       
+ 직접 여러줄의 텍스트를 입력하는 영역 생성.        
```<textarea name="name1" rows="10" cols="20">내용</textarea>```        
#### textarea 속성      
+ name : 텍스트 영역의 이름.        
+ cols : 텍스트 영역의 가로너비(문자기준).
+ rows : 텍스트 영역의 세로길이(줄 단위).   
--------------------------------------------------------------      
## 기타 태그        
### button 태그         
+ 버튼을 만드는 태그.   
```<button type="button">내용</button>```       
#### type 속성의 값.        
+ submit : 폼을 서버로 전송.        
+ reset : 폼에 입력한 내용을 초기화.        
+ button : 버튼 형태만 제작. 
+ CSS를 이용해 스타일을 바꿀 수 있어 ```<input type="image">``` 보다 서버에서 훨씬 빨리 읽어올수 있음.          
### output 태그         
+ 입력값이 계산 결과라는것을 알려주는 태그.     
+ 텍스트와 다르게 표시되지는 않지만 일반 텍스트가 아님을 인식함.        
```
<form oninput="result.value=parseInt(num1.value)+parseInt(num2.value)">
    <input type="number" name="num1" value="0">
    +<input type="number" name="num2" value="0">
    =<output name="result" for="num"></output>
</form>
```         
### progress 태그       
+ 작업 진행 상태를 나타내는 태그.       
```<progress value="50" max="60"></progress>```         
#### progress 태그의 속성    
+ value : 작업 진행상태를 나타냄. 0 이상 max값 이하여야 한다.   
+ max : 작업이 완료되기 까지의 표현.    

+ JS를 이용해 progress 막대의 진행을 순차적으로 계속 진행시킬수 있다.       
### metar 태그          
+ progress 태그와 비슷해보이지만, 전체 크기중 얼마나 차지하는지를 표현하는 태그.        
+ 사용량이나 투표율 등에 사용.          
```<metar value="값" [속성="속성값"]>```            
#### metar 태그의 속성.         
+ min, max : 범위의 최대/최솟값 지정.       
+ value : 범위 내에서 차지하는 값.      
+ low : 하한 값. 최솟값은 아니지만 "이 정도면 낮다" 정도.
+ high : 상한 값. 최댓값은 아니지만 "이 정도면 높다" 정도.      
+ optimum : 적정값. 

