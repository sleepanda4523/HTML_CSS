# CSS 포지셔닝          
## CSS 포지셔닝과 주요 속성들       
### CSS 포지셔닝이란?       
평범한 웹 페이지를 CSS를 이용해 꾸미고, CSS 포지셔닝을 이용해 여러 요소를 적절히 배치한다.          
즉 브라우저 화면 안에 각 콘텐츠 영역을 어떻게 배치할지 결정하는 것.     
### box-sizing 속성 -  박스 너비 기준 정하기        
```box-sizing : content-box | border-box```             
앞에서 배운 width와 height 속성은 박스 모델 안 콘텐츠 부분의 너비.      
= 패딩이나 테두리는 따로 계산해야함.
-> width 값을 콘텐츠 영역 너비 값으로 사용할 지, 패딩이나 테두리를 포함시켜 사용할 지 결정.     
#### 속성 값        
+ **content-box** : width 속성 값을 콘텐츠 영역 너비 값으로 사용. 기본값.       
+ border-box : width 속성 값을 콘텐츠 영역에 테두리까지 포함한 박스 모델 전체 너비 값으로 사용.     
### float 속성 - 왼쪽이나 오른쪽으로 배치하기       
```float: left | right | none```            
웹 요소를 어느 방향으로 배치함.     
#### 속성 값     
+ left : 해당 요소를 문서의 왼쪽으로 배치.      
+ right : 해당 요소를 문서의 오른쪽으로 배치.       
+ none : 좌우 어느쪽으로도 배치하지 않음.       
### clear 속성 - float 속성 해제        
```clear: left | right | none | both```     
float 속성을 이용해 웹 페이지 요소를 왼쪽 또는 오른쪽으로 배치하면 그 다음에 넣는 다른 요소들에게도 똑같은 속성이 전달된다. 
-> float 속성이 필요 없음을 알려주는 속성.      
float: left - clear: left가 기본 형식이지만 float가 left인지 right인지 상관없이 무조건 기본 상태로 되돌리고 싶을 때 clear: borh라고 함.     
