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
단순히 z축만 추가한다고 해서 원근감이 생기지는 않음.        
변형할 때 기준이 되는 지점을 바꾸거나 요소의 원근감을 표현하기 위한 다른 속성도 필요.       
### transform-origin 속성 - 변형 기준점 설정        
```transform-origin: <x축> <y축> <z축> | initial | inherit```       
축이 아닌 특정 지점을 변형의 기준으로 설정하는 속성.        
#### 속성 값        
+ <x축> : 원점 기준 x 좌푯값. 길이, <백분율>, left, center, right 중에 사용가능.        
+ <y축> : 원점 기준 y 좌푯값. 길이, <백분율>, top, center, bottom 중에 사용가능.        
+ <z축> : 원점 기준 z 좌푯값. 길이값만 사용가능.        
+ initial : 기본값. 50% 50% 0.      

### perspective, perspective-origin 속성 - 원근값 표현      
```perspective: <크기> | none```        
3차원 변형에서 사용하는 속성.       
원래위치에서 사용자가 있는 방향으로 잡아당기거나 밀어냄 = 원근감.       
#### 속성 값        
+ <크기> : 원래 위치에서 사용자가 있는 방향으로 얼마나 이동하는지 픽셀로 지정.      
+ **none** : 지정하지 않음. 기본값.     
```perspective-origin: <x축 값> | <y축 값>```       
좀 더 높은 곳에서 원근을 조절하는 듯한 느낌을 만들 수 있다. 
이 속성을 이용하려면 perspective 속성이 함께 지정되어 있어야 함.        
#### 속성 값        
+ <x축값> : 웹 요소가 x축에서 어디에 위치하는지를 지정. 길이값, 백분율, left, center, right 사용가능. 기본값은 50%.       
+ <y축값> : 웹 요소가 y축에서 어디에 위치하는지를 지정. 길이값, 백분율, top, center, bottom 사용가능. 기본값은 50%.  
### transform-style 속성 - 3D 변형 적용하기     
```transform-style: flat | preserve-3d```           
여러가지 변형을 동시에 적용할 때 이 속성을 이용해 부모 요소에 적용한 3D 변형을 하위 요소에도 적용할 수 있다.        
#### 속성 값        
+ flat : 하위 요소를 평면으로 처리.     
+ preserve-3d : 하위 요소들에 3D효과를 적용.        
### backface-visibility 속성 - 요소의 뒷면 표시하기     
```backface-visbility : visible | hidden```         
요소의 뒷면을 표시할 것인지를 결정.     
#### 속성 값        
+ **visible** : 뒷면을 표시한다. 기본 값.       
+ hidden : 뒷면을 표시하지 않는다.      
## 트렌지션     
트렌지션은 하나의 스타일에서 다른 스타일로 완전히 바꾼다.   
스타일이 바뀌는 시간을 조절하면 애니메이션 효과도 낼 수 있다.       
### transition-property 속성 - 트랜지션을 적용할 속성 지정      
```transition-property: all | none | <속성 이름>```     
트랜지션을 어느 속성에 적용할 것인지 선택하는 속성.         
#### 속성 값        
+ **all** : 요소의 모든 속성이 트랜지션 대상이 됨. 기본값.      
+ none : 아무 속성도 지정하지 않음.     
+ <속성 이름> : 트랜지션 효과를 적용할 속성 이름 지정. 여러개인 경우 쉼표로 구분.       
### transition-duration 속성 - 트랜지션 진행 시간 지정          
```transition-duration: <시간>```           
트랜지션 진행 시간을 설정해 애니메이션 효과를 만드는 속성.      
기본값은 0초이며, 시간 단위는 초와 밀리초.      
### transition-timing-function 속성 - 트랜지션 속도 곡선 지정       
```transition-timing-function: linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier(n,n,n,n)```      
트랜지션 시작과 중간, 끝에서의 속도를 지정, 속도 곡선을 만듬.       
#### 속성 값    
+ linear : 시작~끝까지 같은 속도로 트랜지션 진행.       
+ **ease** : 처음에는 천천히, 점점 빨라지다 마지막에 천천히. 기본 값.       
+ ease-in : 시작을 느리게.      
+ ease-out : 느리게 끝냄.       
+ ease-in-out : 느리게 시작, 느리게 끝.     
+ cubic-bezier(n,n,n,n) : 베지에 함수를 직접 정의해 사용. n값은 0~1.        
### transition-delay 속성 - 지연 시간 설정      
```transition-delay: <시간>```          
트랜지션이 언제부터 시작할 것인지를 설정.       
단위는 초와 밀리초.     
### transition 속성 - 트랜지션 속성 한꺼번에 표기하기       
```transition: <transition-property 값> | <transition-duration 값> | <transition-timing-function 값> | <transition-delay 값>```     
꼭 위 순서대로 입력해야 한다.   
## 애니메이션           
### CSS와 애니메이션        
CSS 애니메이션은 트렌지션과 비슷하면서 다른 느낌.       
CSS 애니메이션은 트랜지션과 달리 시작과 끝동안 어디서든 스타일을 바꾸며 애니메이션을 정의할 수 있다.        
애니메이션 중간에 스타일이 바뀌는 지점을 **키프레임**이라고 한다.       
### @keyframe 속성 - 애니메이션 지점 설정       
```
@keyframe <이름> {
    <선택자> { 스타일 }
}
```         
애니메이션의 시작과 끝을 비롯해 상태가 바뀌는 부분이 있다면 이 속성으로 바뀌는 지점을 설정.     
<이름> 은 말그대로 애니메이션 키프레임 이름. 구별용.        
<선택자> 는 스타일 속성 값이 바뀌는 지점. %를 사용해도 되고, from/to라는 키워드를 사용해도 된다.        
### animation-name 속성 - 애니메이션 이름 지정      
```animation-name: <키프레임 이름> | none```        
키프레임 이름을 불러와 애니메이션을 적용하는 속성.      
### animation-duration 속성 - 애니메이션 실행 시간      
```animation-duration: <시간>```        
애니메이션 실행 시간을 지정하는 속성.       
사용할 수 있는 값은 초나 밀리초.    
### animation-direction 속성 - 애니메이션 방향 지정     
```animation-direction: normal | alternate```       
애니메이션이 끝난 후의 설정.        
#### 속성 값        
+ **normal** : 애니메이션을 끝까지 실행한 후 원래 위치로 돌아감. 기본값.         
+ alternate : 애니메이션을 끝까지 실행하면 왔던 방향으로 되돌아가면서 애니메이션을 실행.        
### animation-iteration-count 속성 - 반복 횟수 지정         
```animation-iteration-count: <숫자> | infinite```      
애니메이션 실행 후 반복 실행하는 속성.      
#### 속성 값        
+ <숫자> : 입력한 숫자만큼 반복.        
+ infinite : 무한 반복.     
### animation-timing-function 속성 - 애니메이션 속도 곡선       
```animation-timing-function: linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier(n,n,n,n)```       
애니메이션 전체적인 속도 곡선 지정.         
#### 속성 값    
+ linear : 시작~끝까지 같은 속도로 트랜지션 진행.       
+ **ease** : 처음에는 천천히, 점점 빨라지다 마지막에 천천히. 기본 값.       
+ ease-in : 시작을 느리게.      
+ ease-out : 느리게 끝냄.       
+ ease-in-out : 느리게 시작, 느리게 끝.     
+ cubic-bezier(n,n,n,n) : 베지에 함수를 직접 정의해 사용. n값은 0~1.   
### animation 속성 - 애니메이션 관련 속성 한꺼번에 표기하기         
```
animation: <animation-name> | <animation-duration> | 
            <animation-timing-function> | <animation-delay> | 
            <animation-iteration-count> | <animation-direction>
```         
기본 값을 사용해도 animation-duration 속성 값은 반드시 표기.        
또한 속성 순서는 중요하지 않지만 시간 값이 두개라면     
첫 번쨰 시간은 **animation-time**으로, 두 번째 시간은 animation-delay 속성으로 간주.        
