# CSS3와 애니메이션     
## 변형(transform)      
사용자의 동작에 반응해 텍스트나 이미지 등을 움직이게 할 수 있다.        
### 2차원 변형과 3차원 변형     
2차원 변형은 x,y축으로 이동하며     
3차원 변형은 x,y축에 z축까지 사용해 원근감을 주도록 한다.       
### transform과 변형 함수       
```transform: 변형 함수;```         
웹 요소를 변형하려면 transform 속성을 사용해야 함.      
이때 변형 함수를 함께 입력해주어야 한다.        
#### 2차원 변형 함수      
이전 브라우저를 위해 브라우저 접두사를 붙여줘야 한다.         
+ translate(tx,ty) : 지정한 크기만큼 x y축으로 이동.        
+ translateX(tx) : 지정한 크기만큼 x축으로 이동.        
+ translateY(ty) : 지정한 크기만큼 y축으로 이동.        
+ scale(sx,sy) : 지정한 크기만큼 x y축으로 확대/축소.       
+ scaleX(sx) : 지정한 크기만큼 x축으로 확대/축소.  
+ scaleY(sy) : 지정한 크기만큼 y축으로 확대/축소.       
+ rotate(각도) : 지정한 각도만큼 회전.      
+ skew(ax,ay) : 지정한 각도만큼 x y축으로 왜곡.     
+ skewX(ax) : 지정한 각도만큼 x축으로 왜곡.     
+ skewY(ay) : 지정한 각도만큼 y축으로 왜곡.         
#### 3차원 변형 함수        
+ matrix3d(n[,n]) : 4*4 행렬을 이용해 이동과 확대/축소, 회전 등으 변환을 지정.      
+ translate3d(tx,ty,tz) : 지정한 크기만큼 x y z축으로 이동.     
+ translateZ(tz) : 지정한 크기만큼 z축으로 이동.        
+ scale3d(sz,sy,sz) : 지정한 크기만큼 x y z축으로 확대/축소.        
+ scaleZ(sz) : 지정한 크기만큼 z측으로 확대/축소.       
+ rotate3d(rx,ry,rz, 각도) : 지정한 각도만큼 회전.      
+ rotateX(각도) : 지정한 각도만큼 x축으로 회전.  
+ rotateY(각도) : 지정한 각도만큼 y축으로 회전.  
+ rotateZ(각도) : 지정한 각도만큼 z축으로 회전.         
+ perspective(길이) : 입체적으로 보일 수 있는 깊이 값을 지정.       
-------------------------------------       
여기서부턴 설명이 부족한 변형 함수만 적어놓을 예정.     
### rotate 변형 함수 - 요소 회전하기        
2차원 함수 기본형       
```transform: rotate(각도);```       
3차원 함수 기본형       
```
transform: rotate(rx,ry,각도);
transform: rotate3d(rx,ry,rz,각도);
transform: rotateX(각도);
transform: rotateY(각도);       
transform: rotateZ(각도);       
```         
2차원은 간단하니 넘어가고,          
3차원에서 rotate3d()에서 rx,ry,rz는 각각 방향 벡터를 나타낸다.      
------------------------------------------          
## 변형과 관련된 속성들     

   
