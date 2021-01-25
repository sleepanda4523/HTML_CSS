# 레이아웃을 위한 스타일        
## CSS와 박스 모델          
박스형태의 모델이 모여 웹 문서를 이룬다. CSS에서 자주 사용되는 개념.    
### 블록 레벨 요소와 인라인 레벨 요소           
박스 모델은 블록 레벨 요소인지 인라인 레벨 요소인지에 따라 나열 방법이 달라짐.      
+ 블록 레벨 : 태그를 사용해 요소를 삽입했을 때 혼자 한 줄을 차지하는 요소.          
= 해당 요소의 너비가 100%라는 의미. -> 그 요소의 양옆에 다른 요소가 올 수 없다.         
너비, 마진, 패딩 등을 이용해 크기나 위치를 지정하려면 블록레벨요소여야 한다.            
```<div>, <p>```태그가 대표적 블록레벨요소.         
+ 인라인 레벨 : 줄을 차지하지 않는 요소.        
= 화면에 표시되는 콘튼츠만큼만 영억을 차지. -> 나머지 공간에 다른 요소가 올 수 있다.        
```<img>, <strong>```태그 등이 대표적 인라인레벨 요소.      
### 박스 모델 - 박스 형태의 콘텐츠          
블록 레벨 요소는 모두 박스 형태.        
박스 모델은 실제 콘텐츠 영역, 박스와 콘텐츠 사이 여백인 패딩, 박스의 테두리(border), 여러 박스 모델 사이의 여백인 마진 등의 요소로 구성.        
### width, height 속성 - 콘텐츠 영역의 크기         
```
width : <크기> | <백분율> | auto;
height : <크기> | <백분율> | auto;
```         
width는 콘텐츠 영역의 너비, height는 콘텐츠 영역의 높이를 결정한다.     
#### 속성 값        
+ <크기> : px, cm와 같은 단위로 크기를 결정.        
+ <백분율> : 박스 모델을 포함하는 부모 요소를 기준으로 너비나 높이 조정.        
-> 만약 부모요소가 ```<body>```인 경우 웹 문서 창의 크기에 따라 달라진다.           
+ **auto** : 콘텐츠 양에 따라 자동으로 결정. 기본 값.       
#### 실제 콘텐츠 크기 계산하기      
보통 브라우저에서 박스 모델의 전체 너비는 width + 좌우 패딩 + 좌우 테두리인데,          
인터넷 익스플로러 6에서 CSS를 처리할 때는 width = 콘텐츠 너비 + 좌우 패딩 + 좌우 테두리로 계산함.       
-> 익스플로러6를 고려한다면 박스 모델의 width 값을 주의.        
### display 속성 - 화면 배치 방법 결정      
```display : none | contents | block | inline | inline-block | table | table-call 등```         
+ 원래는 해당 요소가 화면에 어떻게 보일지 지정할 때 사용하는 속성.      
-> 블록 레벨 요소와 인라인 레벨 요소를 지정할 수 있음.      
#### 자주 사용하는 속성 값      
+ block : 해당 요소를 블록 레벌로 지정. ```<img>```같은 인라인 레벨 요소도 블록 레벨 요소로 바꾼다.     
+ inline : 해당 요소를 인라인 레벨로 바꾼다.        
```<ul> <li>```같은 블록레벨 요소도 인라인 레벨요소로 바꾼다.       
+ inline-block : 요소를 인라인 레벨로 배치하면서 너비, 마진 등 블록 레벨 요소를 지정하고 싶을 때 사용.          
 = 인라인 레벨 요소이면서 블록 레벨 속성을 지님.            
+ none : 해당 요소를 화면에 아예 표시하지 않고 공간도 차지하지 않음.        
```visvility : hidden```는 화면만 감출 뿐 공간은 차지.      
## 테두리 관련 속성     
테두리 두께, 테두리 스타일, 테두리 색상 등이 있다.      
### border-style 속성 - 테두리 스타일       
```border-style : none | hidden | dashed | dotted | double | groove | inset | outset | ridge | solid```         
실선, 점선, 이중선 등 테두리의 스타일을 지정.       
#### 속성 값        
+ none : 테두리가 나타나지 않는다. 기본 값.
+ hidden : 테두리가 나타나지 않는다. border-collapse:collapse인 경우, 다른 테두리도 표시되지 않는다.            
+ dashed : 테두리를 직선으로 된 점선으로 표시.
+ dotted : 테두리를 점선으로 표시.
+ double : 테두리를 이중선으로 표시. 두 선 사이의 간격은 border-width로 지정.           
+ groove : 홈이 파인듯한 입체적 테두리.     
+ inset : border-collapse:separate인 경우, 각지게 튀어나와 보이고
          border-collapse:collapse인 경우, groove와 똑같이 보임.
+ outset : border-collapse:separate인 경우, 각지게 튀어나와 보이고
           border-collapse:collapse인 경우, ridge와 똑같이 보임.
+ ridge : 테두리가 양 옆으로 각지고, 충에서 튀어나온 것처럼 표시.
+ solid : 테두리를 실선으로 표시.
### border-width 속성 - 테두리 두께         
```
border-top-width : <크기> | thin | medium | thick
border-right-width : <크기> | thin | medium | thick
border-bottom-width : <크기> | thin | medium | thick
border-left-width : <크기> | thin | medium | thick
border-width : <크기> | thin | medium | thick
```         
각 방향 테두리마다 따로 두께를 지정할 수도 있고, 한꺼번에 지정할 수도 있다.         
border-width속성으로 4방향 따로따로 지정할 때, top부터 시계방향으로 두께를 지정한다. (top->right->bottom->left)         
```border-width : 5px 10px 15px 20px```         
### border-color 속성 - 테두리 색상         
```
border-top-color : <색상>
border-right-color : <색상>
border-bottom-color : <색상>
border-left-color : <색상>
border-color : <색상>
```         
각 방향마다 따로 색상을 지정할 수 있고, 한꺼번에 지정할 수도 있다.      
### border 속성 - 테두리 스타일 묶어 지정하기       
```
border-top: <두께> | <색상> | <스타일>      
border-right: <두께> | <색상> | <스타일>      
border-bottom: <두께> | <색상> | <스타일>      
border-left: <두께> | <색상> | <스타일>      
border: <두께> | <색상> | <스타일>      
```         
지금까지 나온 테두리 두께, 색상, 스타일을 묶어 표현.
추가로 두께, 색상, 스타일 순서는 상관 없다.         
### border-radius 속성 - 박스 모서리 둥글게 만들기          
```
border-top-left-radius: <크기> | <백분율>           
border-top-right-radius: <크기> | <백분율>           
border-bottom-left-radius: <크기> | <백분율>           
border-bottom-right-radius: <크기> | <백분율>           
border-radius: <크기> | <백분율>           
```         
모서리 부분에 원이 있는 것처럼 생각하고 원의 반지름 값을 지정.      
#### 속성 값            
+ <크기> : 반지름크기를 px, em같은 단위와 함께 수치로 표시.         
+ <백분율> : 현재 요소의 크기를 기준으로 둥글게 처리할 반지름 크기를 %로 지정.      
#### 타원 형태로 둥글게 만들기          
저 속성 값에서 가로크기와 세로크기를 크기 값이나 백분율로 지정해주면 된다.      
### box-shadow - 선택 요소에 그림자 효과 내기        
```box-shadow: none|<그림자값>```             
```<그림자 값> = <수평거리> <수직거리> <흐림정도> <번짐정도> <색상> inset```          
그림자 추가 속성.           
#### 속성 값            
+ <수평거리> : 수평으로 얼만큼 떨어져 있나. 양수는 요소의 오른쪽, 음수는 왼쪽. **필수 속성.**           
+ <수직거리> : 세로로 얼마나 떨어져 있나. 양수는 요소의 아래쪽, 음수는 위쪽. **필수속성**       
+ <흐림정도> : 0을 기본값으로 진한그림자 -> 부드러운 그림자.        
+ <번짐정도> : 그림자의 번지는 정도. 양수는 모든 방향으로 퍼지고, 음수는 모든방향으로 축소되어 보임.            
+ <색상> : 그림자의 색상으로 지정. 공백으로 구분해 여러 개의 색상을 지정할 수도 있음.       
+ inset : 이 키워드를 사용하면 안쪽 그림자로 표시.      
## 여백을 조절하는 속성들       
마진과 패딩을 조절, 디자인. 박스 모델에서 활용도가 높다.        
### margin - 요소 주변 여백 설정        
```
margin-top: <크기>|<백분율>|auto        
margin-right: <크기>|<백분율>|auto        
margin-bottom: <크기>|<백분율>|auto        
margin-left: <크기>|<백분율>|auto        
margin: <크기>|<백분율>|auto        
```     
현재 요소 주변의 여백. 한 요소와 다른 요소 사이이 간격을 조절.  
margin에서 값이 2개면 상하/좌우.        
3개이상이면 top->right->bottom->left 순서.     
#### 속성 값        
+ <크기> : px, cm 같은 단위와 함께 수치로 지정.         
+ <백분율> ; 박스 모델을 포함하고 있는 부모 요소를 기준으로 % 지정.     
+ auto : display 속성에서 지정한 값에 맞게 적절한 값을 자동으로 지정.       
### padding - 콘텐츠 영역과 테두리 사이 간격        
```
padding-top: <크기>|<백분율>|auto       
padding-right: <크기>|<백분율>|auto       
padding-bottom: <크기>|<백분율>|auto       
padding-left: <크기>|<백분율>|auto       
padding: <크기>|<백분율>|auto       
```         
콘텐츠 영역과 테두리 사이의 여백을 설정.        
속성값은 margin과 사용법이 비슷함.      



