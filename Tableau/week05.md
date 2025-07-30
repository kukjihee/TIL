## 23강
### 지도 
* 범례 앞에 ABC 클릭 => 지리적 역할 추가
* 혹은...지리적 역할 추가 => 만들기 원본 수행해서 계층 구조 만들기
* 마크카드에서 자동 => 맵 으로 변경   
  
<img width="677" height="682" alt="화면 캡처 2025-07-30 164831" src="https://github.com/user-attachments/assets/350c3e8f-0dd1-4612-8d10-59645f186f87" />   

* 마크카드에서 자동=> "밀도"로 설정
* 색상도 변환 가능
  
<img width="632" height="677" alt="화면 캡처 2025-07-30 165208" src="https://github.com/user-attachments/assets/697e436f-01a0-4022-b242-5bb5c51ca5aa" />   


 <지도 장단점>   
 장점: 눈에 잘 들어오고 직관적임 => 데이터에 공간적 맥락을 부여   
 단점: 데이터 집계 결과를 면적을 가진 지도 위에 표현하기 때문에 왜곡 발생 가능성 있음   

 ## 24강   
 ### 계산된 필드   
 데이터에 있는 필드를 활용해 새로운 필드를 만드는 작업   
  Ex) sum([Profit])/sum([Sales])      
<img width="635" height="661" alt="화면 캡처 2025-07-30 170642" src="https://github.com/user-attachments/assets/e3e6af35-f0bf-4c75-aa16-1d7e852b19e2" />


## 25강   
### IF 함수
<img width="637" height="677" alt="화면 캡처 2025-07-30 171024" src="https://github.com/user-attachments/assets/7f4f7b18-64ec-442f-ada6-dbb41599ce5d" />   
<img width="631" height="680" alt="화면 캡처 2025-07-30 171105" src="https://github.com/user-attachments/assets/add7dd93-97a2-4182-a9ac-226288bb5034" />

Ex)    
IF SUM([Sales])>=100000 then 'High' else 'Low' END   
이거랑   
IIF ( SUM([Sales])>=100000, 'High','Low' )   
이거랑 같은 표현 법!!   


Ex2) 2가지 범주 이상으로 분류하는 법   
IF SUM([Sales])>=100000 then 'High'    
elseif SUM([Sales])>= 50000 then 'Middle'    
else 'Low' END   

## 수강인증   
<img width="291" height="352" alt="화면 캡처 2025-07-30 171810" src="https://github.com/user-attachments/assets/1e29367c-d2d9-48c9-87dc-055d8fdd1df9" />

