# 통계학 1주차 정규과제

📌통계학 정규과제는 매주 정해진 분량의 『*데이터 분석가가 반드시 알아야 할 모든 것*』 을 읽고 학습하는 것입니다. 이번 주는 아래의 **Statistics_1st_TIL**에 나열된 분량을 읽고 `학습 목표`에 맞게 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 추가자료와 교재를 다시 참고하여 보완하는 것이 좋습니다.

1주차는 `1부. 데이터 기초체력 기르기`를 읽고 새롭게 배운 내용을 정리해주시면 됩니다.


## Statistics_1st_TIL

### 1부. 데이터 기초체력 기르기
### 01. 통계학 이해하기
### 02. 모집단과 표본추출
### 03. 변수와 척도
### 04. 데이터의 기술 통계적 측정
### 05. 확률과 확률변수

## Study Schedule

|주차 | 공부 범위     | 완료 여부 |
|----|----------------|----------|
|1주차| 1부 p.2~56     | ✅      |
|2주차| 1부 p.57~79    | 🍽️      | 
|3주차| 2부 p.82~120   | 🍽️      | 
|4주차| 2부 p.121~202  | 🍽️      | 
|5주차| 2부 p.203~254  | 🍽️      | 
|6주차| 3부 p.300~356  | 🍽️      | 
|7주차| 3부 p.357~615  | 🍽️      | 

<!-- 여기까진 그대로 둬 주세요-->

# 01. 통계학 이해하기

```
✅ 학습 목표 :
* 통계학의 필요성에 대해 인식한다.
* 기술통계와 추론통계의 특성을 구분할 수 있다.
```
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->
*기술통계: 문자 그대로 주어진 데이터의 특성을 사실에 근거하여 설명/묘사   
-> 전체 데이터를 쉽고 직관적으로 파악할 수 있도록 설명   
-> 보통 시각화를 많이 사용하여 효과적으로 표현   

*추론통계: 표본 집단으로부터 모집단의 특성을 추론하는 것 
<img width="250" alt="Image" src="https://github.com/user-attachments/assets/8dc4e220-68ec-466b-a661-805160cad043" />   

   
# 02. 모집단과 표본추출

```
✅ 학습 목표 :
* 모집단과 표본의 정의와 관계를 설명할 수 있다.
* 편향과 분산의 차이를 설명할 수 있다.
```

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->
최종분석에서 전체 데이터를 사용하더라도, 분석 모델이 완성될 때까지는 표본 데이터를 활용하는 것이 경제적, 시간적으로 유리함.   
-> 데이터는 어느 정도 이상 확보되면 모수와 표본 통계량의 차이가 거의 없음   

표본 오차(우연, 표본 수 부족...) vs 비표본오차(조사원의 미숙, 자료의 그릇된 해석, "편향" ...)   
<img width="260" alt="화면 캡처 2025-03-24 110022" src="https://github.com/user-attachments/assets/8e88eba0-70f6-406c-87b2-0d5ea9df3394" />


편향과 분산은 트레이드오프 관계.    
예) 표적에 총을 쐈을 때 타깃과 좀 떨어지더라도 모든 구멍이 일정하게 모여있음 = 분산이 작다   
타깃 주변으로 구멍이 몰린 상황 = 편향이 적다   
<img width="219" alt="화면 캡처 2025-03-24 110049" src="https://github.com/user-attachments/assets/402acff6-c74c-40fd-8429-52dc8a11db5f" />   

   

# 03. 변수와 척도
```
✅ 학습 목표 :
* 독립변수, 종속변수의 관계를 파악할 수 있다.
* 척도(변수의 데이터적 속성)의 종류를 설명할 수 있다.
```
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->
독립변수: 설명/입력/예측(=x)      
종속변수: 반응/출력/피예측(=y)   
<img width="241" alt="화면 캡처 2025-03-24 110203" src="https://github.com/user-attachments/assets/fed1716b-e540-40a5-b6ef-8d248de16429" />   


*척도종류   
A)질적척도   
  1)명목척도: 성별     
  2)서열척도: 석차      
B)양적척도   
  1)등간척도: 온도   
    -> 절대원점 X   
  2)비율척도: 몸무게   
    -> 절대원점 O     
    
<img width="346" alt="화면 캡처 2025-03-24 110233" src="https://github.com/user-attachments/assets/d1cb9f6c-c0a1-4428-9fa5-f15ad4e2e4b4" />   


       
# 04. 데이터의 기술 통계적 측정

```
✅ 학습 목표 :
* 산포도의 의미를 설명하고 측정방법을 나열할 수 있다.
* 정규분포의 왜도값과 첨도값이 얼마인지 답할 수 있다.
```

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->
산포도: 대푯값을 중심으로 자료들이 흩어져 있는 정도    
-> 분산, 표준편차를 포괄하는 상위 개념   
-> 측정법: 범위/분산/표준편차/사분위수 범위/변동계수 등   

왜도: 데이터 분포의 좌우 비대칭도를 표현하는 척도(즉, 데이터의 분포가 얼마나 대칭인지아닌지)   
-> 정규분포는 평균값,중앙값,최빈값이 일치하여 왜도는 0이됨   
<img width="283" alt="화면 캡처 2025-03-24 110419" src="https://github.com/user-attachments/assets/5565bd9d-bc34-4730-aa3e-0ecd07f73ef4" />

첨도: 분포가 정규분포보다 얼마나 뾰족하거나 완만한지 정도를 나타내는 척도   
-> 정규분포의 첨도 기준이 0일 때 첨도가 음수로 작을수록 분포는 넓게 퍼져있게 되고 양수로 클수록 뾰족한 형태의 분포를 갖게됨.   
<img width="180" alt="화면 캡처 2025-03-24 110434" src="https://github.com/user-attachments/assets/6c0a5f7b-3114-4b32-8d65-174ebe0ea7a6" />

# 05. 확률과 확률변수

```
✅ 학습 목표 :
* 확률변수의 개념과 종류를 설명할 수 있다.
* 심슨의 역설을 설명하고, 발생 원인을 식별하며, 이를 해결하기 위한 방안을 도출할 수 있다.
```
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->
확률변수: 측정 값이 변할 수 있는 확률이 주어진 변수     
1)이산확률변수   
2)연속확률변수   
<img width="276" alt="화면 캡처 2025-03-24 110532" src="https://github.com/user-attachments/assets/d17a2691-c1b8-4f4e-950f-f534d49d204a" />   

   

심슨의 역설  
통계적 결론이 나왔을 때, 항상 의심을 갖고서 데이터의 원천 단계부터 결과의 원인을 확인하는 습관을 갖도록 해야함   

<br>
<br>

# 확인 문제

## 문제 1.

> **🧚Q. 한 대형 병원이 두 명의 외과 의사(A와 B)의 수술 성공률을 비교하려고 한다. 과거 1년간의 데이터를 보면, A 의사의 전체 수술 성공률은 80%, B 의사의 전체 수술 성공률은 90%였다. 이 데이터를 본 병원 경영진은 A 의사의 실력이 B 의사보다 별로라고 판단하여 A 의사의 수술 기회를 줄이는 방향으로 정책을 조정하려 한다.
그러나 일부 의료진은 이 결론에 의문을 제기했다.
그들은 "단순한 전체 성공률이 아니라 더 세부적인 데이터를 분석해야 한다"고 주장했다.**

> **-A 의사의 실력이 실제로 B 의사보다 별로라고 결론짓는 것이 타당한가?   
-그렇지 않다면, 추가로 확인해야 할 정보는 무엇인가?**

<!--심슨의 역설을 이해하였는지 확인하기 위한 문제입니다-->

<!--학습한 개념을 활용하여 자유롭게 설명해 보세요. 구체적인 예시를 들어 설명하면 더욱 좋습니다.-->

```
 A 의사와 B 의사의 전체 수술 성공률만 비교하는 것이 잘못된 결론을 유도할 수 있다는 점에서 심슨의 역설이 발생할 수 있다.
예를 들어, A 의사와 B 의사는 서로 다른 유형의 환자를 수술했을 수 있다. A 의사는 더 어려운 수술을 많이 했고, B 의사는 상대적으로 더 쉬운 수술을 했을 수 있다. 환자들의 상태나 수술의 난이도에 따라 수술 성공률이 달라질 수 있기에 수술의 난이도별 성공률을 별도로 확인해야 할 필요가 있다.
```

### 🎉 수고하셨습니다.
