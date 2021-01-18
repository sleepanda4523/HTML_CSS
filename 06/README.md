# 텍스트 관련 스타일        
## 글꼴 관련 스타일     
### font-family 속성 - 글꼴지정     
```font-family:"글꼴이름", "글꼴이름2"```       
+ 텍스트의 글꼴을 지정.         
+ 여러개의 글꼴을 지정하는 이유는 사용자가 지정한 글꼴이 시스템에 없는 경우를 대비해 지정.   
+ font-family속성은 상속됨.         
### @font-face 속성 - 웹 폰트 사용      
+ 사용자 시스템에 없는 글꼴을 그대로 보여주기 위해 웹 문서에 글꼴 정보도 함께 저장 -> 사용자 시스템에 다운로드시키는 방식 = 웹 폰트         
[웹 폰트](https://fonts.google.com)         
 1. 위 사이트에 원하는 웹 폰트를 찾아 클릭한다.        
 2. 오른쪽의 **Select the font** = +아이콘을 클릭.      
 3. 원하는 글꼴을 다 선택했다면, 맨 위 상단 **View your selected families** 버튼을 누르면 자신이 고른 폰트가 저장되어 있으며,           
 4. **Use on the web**탭의 html코드를 복사해 head태그 안에 붙여넣는다.   
#### 직접 웹 폰트 업로드해 사용하기     
+ 만약 자신이 가지고 있는 폰트를 사용하고 싶다면 직접 업로드를 해야 함.   
+ 보통 컴퓨터에서 사용하는 글꼴은 트루타입. .ttf이다. -> 무겁다!   
-> 가벼운 글꼴 유형 중 우리는 eot와 woff파일이 많이 사용됨.   
[웹 폰트 변환 사이트](https://transfonter.org)      

```
@font-face {
    font-family:'글꼴이름';
    src: url('글꼴파일경로') format('파일 유형')
}
```         
+ 혹시라도 woff파일이나 eot파일을 지원하지 않는 브라우저를 고려해서 eot, woff, ttf 순으로 선언해주어야 한다.        
```
@font-face {
    font-family:'font1';
    src : local('font1')
        url('font1.eot')
        url('font1.woff') format('woff')
        url('font1.ttf') format('truetype')
}
```         
### font-size 속성 - 글자크기 조절          
```font-size: <절대크기> <상대크기> <크기> <백분율>```      
+ 절대크기 : 브라우저에서 지정한 클자 크기. 
 xx-smail, x-smail, smail, medium, large, x-large, xx-large
+  상대크기 : 부모요소의 글자크기를 기준으로 지정.
 larger, smailer
+ 크기 : 브라우저와 상관없이 글자 크기 지정.
+ 백분율 : 부모요소의 글자크기를 기준으로 해당하는 %를 계산해 표시.     

보통 **크기**값을 직접 지정함.      
#### 크기 값의 단위         
+ em : 해당 글꼴의 대문자 **M**의 너비를 기준.      
+ ex : 해당 글꼴의 소문자 **x**의 높이를 기준.      
+ px : 픽셀. 모니터에 따라 상대적 크기가 됨.        
+ pt : 포인트. 일반적 문서에서 많이 사용.       
-> 주로 px단위를 많이 사용.         
하지만 px는 폰트크기가 고정되기 때문에 작은화면에는 작은 글씨로 표시.   
-> 모바일 접속까지 고려한다면 em단위가 좀더 좋다.       
+ em은 글꼴에 따라 다르지만 통상적으로 16px = 1em이라고 생각하면 된다. 
### font-weight 속성 - 글자 굵기 지정           
``` font-weight: normal | bold | bolder | lighter | 100~900 ```     
 #### 사용하는 속성 값          
  + normal : 일반적인 형태. 기본값.         
  + bold | lighter | bolder : 굵게 | 원래 굵기보다 얇게 | 원래 굵기보다 굵게.           
  + 100~900 : 400 = normal, 700 = bold. 글자 굵기를 세밀히 조정가능.    
### font-variant 속성 - 작은 대문자     
```font-variant : normal | small-caps```        
 + 작은 대문자란 대문자를 소문자 크기에 맞추어 표시하는것.      
### font-style 속성 - 글자 스타일 지정.   
```font-style : normal | italic | oblique ```         
 + 글자를 이텔릭체, 즉 기울일 때 사용하는 속성.    
 + **italic** 속성 값은 글꼴에 기울어진 글꼴이 디자인되어 있어 그것을 불러오는 반면, **oblique**속성 값은 원래 글꼴을 기울여 표시.  
 + 보통 글꼴에 이텔릭체가 포함되어 있어 웹에서는 **italic**을 사용.    
### font 속성 - 글꼴 속성을 묶은 속성       
``` font : <font-style><font-variant><font-size/line-height><font-family> | caption | icon | message-box | small-caption | status-bar```            
 + 위에 나왔던 모든 속성들을 한꺼번에 묶어 약식으로 표현할 수 있다.     
 + 또한 특정 키워드를 입력해 그것에 어울리는 글꼴 스타일로 표시할 수 있다.      
 #### font 키워드       
 + font-* : **font-**로 시작하는 글꼴 관련 속성을 한꺼번에 나열.      
 + caption : **캡션**(짧은 해설)에 어울리는 글꼴 스타일로 표시.     
 + icon : **아이콘**에 어울리는 글꼴 스타일로 표시.         
 + menu : **드롭다운 메뉴**에 어울리는 글꼴 스타일로 표시.      
 + message-box : **대화상자**에 어룰리는 글꼴 스타일로 표시.        
 + small-caption : **작은 캡션**에 어울리는 글꼴 스타일로 표시.         
 + status-bar : **상태 표시줄**에 어울리는 글꼴 스타일로 표시.          
+ **font-size/line-height**는 슬래시(/)로 연결해 함께 표현. 
 line-height는 줄 간격을 설정하는 속성.         
-----------------------------------------------         
## 텍스트 스타일        
+ 글자, 단어, 문단에서 사용되는 스타일.         
### color 속성 - 글자 색 지정       
```color : <색상>```        
+ 텍스트의 글자 색을 바꿀 때 사용됨.    
+ 색상 값은 16진수, rgb(), hsl(), 색상이름(ex:blue)등으로 표기.     
### text-decortion 속성 - 텍스트에 줄 표시하기/없애기       
```text-decoration : none | underline | overline | line-through;```   
+ 텍스트에 밑줄 혹은 취소선을 그을 수 있다.         
#### 속성 값        
 + none : 밑줄을 표시하지 않는다.           
 + underline : 밑줄을 표시한다.     
 + overline : 영역 위로 선을 그린다.        
 + line-through : 취소선을 그린다.      
### text-transform 속성 - 텍스트 대소문자 변환하기      
```text-transform : none|capitalize|uppercase|lowercase|full-width```           
+ 텍스트의 대소문자를 원하는 대로 바꿀 수 있다.         
#### 속성 값            
 + none : 변환하지 않는다.      
 + capitalize : 시작하는 첫 번째 글자만 대문자로 변환한다.      
 + uppercase : 모든 글자를 대문자로.    
 + lowercase : 모든 글자를 소문자로.
 + full-width : 가능한 모든 문자를 **전각문자**(두배의 너비)로.         
### text-shadow 속성 - 텍스트에 그림자 효과 추가            
```text-shadow : none|<가로거리><세로거리><번짐정도><색상>```           
+ 텍스트에 그림자 효과를 넣음.          
#### 속성 값        
 + <가로거리> : 텍스트-그림자까지의 가로 거리. 양수는 오른쪽, 음수는 왼쪽.
 + <세로거리> : 텍스트-그림자까지의 세로 거리. 양수는 아래쪽, 음수는 위쪽.
 -> 위 둘은 필수 속성이다. 단위는 px.       
 + <번짐정도> : 그림자가 번지는 정도. 양수값은 모든방향으로 크게, 음수는 축소되어 표시. 기본값은 0.
 + <색상> : 그림자 색상을 지정. 공백으로 구분해 여러개도 가능. 기본값은 현재 글자 색.       
### white-space 속성 - 공백 처리하기        
```white-space : normal|nowrap|pre|pre-line|pre-wrap```         
+ 여러개의 공백의 처리 방식을 지정.     
#### 속성 값        
 + normal : 여러개의 공백을 하나로 표시.        
 + nowrap : 여러개의 공백을 하나로 표시 + 영역 너비를 넘어가는 내용은 줄바꿈 x. -> 그냥 한 줄로 표시.       
 + pre : 여러개의 공백 그대로 표시. + 영역 너비를 넘어가는 내용은 줄바꿈 x. -> 그냥 한 줄로 표시.
 + pre-line : 여러개의 공백을 하나로 표시. + 영역 너비를 넘어가는 내용은 자동으로 줄 바꿈.     
 + pre-wrap : 여러개의 공백을 그대로 표시. + 영역 너비를 넘어가는 내용은 자동으로 줄 바꿈.      
### letter-spacing과 word-spacing 속성      
```
letter-spacing : normal | <크기>
word-spacing : normal | <크기>
```         
+ 텍스트 자간을 조정. letter는 글자, word는 단어 자간 조절. -> 보통 letter를 많이 씀.           
+ 자간의 단위는 대문자 M을 기준으로 하는 **em**을 사용. (글꼴)      
------------------------------------------
## 문단 스타일          
텍스트 정렬, 들여쓰기, 줄 간격 등.      
### direction 속성 - 글자 쓰기 방향     
```direction : ltr | rtl```         
+ 텍스트 방향 지정.     
#### 속성 값        
 + ltr : 왼쪽 -> 오른쪽. 기본값.        
 + rtl : 오른쪽 -> 왼쪽.        
### text-align 속성 -  텍스트 정렬하기          
```text-align : start|end|left|right|center|justify|match-parent```     
+ 텍스트 정렬 방식 지정.        
#### 속성 값            
 + start : 현재 텍스트 줄의 시작 위치에 맞추어 문단을 정렬. 
   ltr이라면 왼쪽, rtl이라면 오른쪽.            
 + end : 현재 텍스트 줄의 끝 위치에 맞추어 문단을 정렬. 
   ltr이라면 오른쪽, rtl이라면 왼쪽.  
 + left : 왼쪽에 맞추어 문단을 정렬.            
 + right : 오른쪽에 맞추어 문단을 정렬.         
 + center : 가운데에 맞추어 문단을 정렬.        
 + justify : 양쪽에 맞추어 문단을 정렬.     
 + match-parent : 부모 요소를 따라 문단을 정렬.         
### text-justify 속성 - 정렬 시 공백 조정           
```text-justify : auto|none|inter-word|distribute```            
+ 위에서 텍스트를 정렬할 때 속성 값이 **justify**일 경우, 글자와 단어 사이 간격이 어색하게 벌어질 수 있음.      
+ 이때 이 간격을 조절하는 속성.         
#### 속성 값            
 + auto : 웹 브라우저에서 자동으로 지정.
 + none : 정렬하지 않는다.      
 + inter-word : 단어 사이의 공백을 조절, 정렬한다.      
 + distribute : 인접한 글자 사이의 공백을 똑같이 맞추어 정렬.    
### text-indent 속성 - 텍스트 들여쓰기      
```text-indent : <크기>|<백분율>   ```              
+ 텍스트 문단의 첫 글자를 얼마나 들여쓸지 지정.         
#### 속성 값        
 + <크기> :  px단위. 들여 쓸 크기 지정. 음수도 가능.        
 + <백분율> : 부모요소의 너비를 기준으로 상대적 크기 지정.      
### line-height 속성 - 줄 간격 조절하기         
```line-height : normal|<숫자>|<크기>|<백분율>|inherit```           
+ 줄 간경을 조정.       
#### 속성 값        
 + normal : 변동없음.       
 + <숫자> : 몇 배수를 뜻함. 2 = 2배.
 + <크기> : 실제 크기. px단위. 
 + <백분율> : 글자 크기를 기준으로 백분율 설정.     
 + inherit : 부모 요소의 속성값을 상속.     
### text-overflow 속성 - 넘치는 텍스트 표기하기         
```text-overflow: clip | ellipsis```            
+ 텍스트가 기준선을 넘어갈 때 처리방식을 지정.(white-space:nowrap)    
+ 또한 overflow 속성값이 **hidden**, **scroll**, **auto** 일때 가능.        
-------------------------------------------   
## 목록 스타일      
목록을 만드는 스타일 속성.      
### list-style-type 속성 - 목록의 불릿과 번호 스타일 지정       
```list-style-type : none | <순서 없는 목록의 불릿> | <순서 목록의 번호>```       
#### 순서 없는 목록에서 불릿 모양 바꾸기        
+ disc : 채운 원
+ circle : 빈 원
+ square : 채운 사각형
+ none : 불릿 없애기      
#### 순서 목록에서 숫자 바꾸기      
+ decimal : 1로 시작하는 십진수
+ decimal-leading-zerd : 앞에 0이 붙는 십진수
+ lower-roman : 소문자 로마 숫자      
+ upper-roman : 대문자 로마 숫자    
+ lower-alpha 또는 lower-latin : 소문자 알파벳        
+ upper-alpha 또는 upper-latin : 대문자 알파벳        
### list-style-image 속성 - 불릿 대신 이미지 넣기     
```list-style-image : <이미지>|none | <이미지>=url(이미지파일경로)```   
#### 속성 값      
+ none : 이미지를 사용하지 않고 list-style-type에서 지정한 형태로 표시.
+ <이미지> : url(경로)형태로 이미지를 가져옴.     
### list-style-position 속성 - 목록에 들여쓰는 효과 내기      
```list-style-position : inside | outside```        
#### 속성 값      
+ inside : 불릿이나 숫자를 안쪽으로 들여 씁니다.      
+ outside : 기본 값으로 불릿이나 숫자를 밖으로 내어 씁니다.   
### list-style 속성 - 목록 속성 한꺼번에 표시하기     
위에 설명한 **list-style-...** 속성을 한꺼번에 표시할 수 있다.    
```
ul {
  list-style-type : lower-alpha;
  list-style-position : inside;
}
```     
-> 
``` 
ul {
  list-style : lower-alpha, inside;
}
```       





