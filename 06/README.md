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
