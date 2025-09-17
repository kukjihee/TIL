# SQL_ADVANCED 3주차 정규 과제 

## Week 3: 윈도우 함수 (Window Functions)

📌**SQL_ADVANCED 정규과제**는 매주 정해진 주제에 따라 **MySQL 공식 문서 또는 한글 블로그 자료를 참고해 개념을 정리한 후, 이번 주차에는 LeetCode SQL 문제 3문제**와 **추가 확인문제**를 직접 풀어보며 학습하는 과제입니다. 

이번 주는 아래의 **SQL_ADVANCED_3rd_TIL**에 나열된 주제를 중심으로 개념을 학습하고, 주차별 **학습 목표**에 맞게 정리해주세요. 정리한 내용은 GitHub에 업로드한 후, **스프레드시트의 'SQL' 시트에 링크를 제출**해주세요. 



**(수행 인증샷은 필수입니다.)** 

> Leet code의 문제를 풀고 '정답입니다' 문구를 캡쳐해서 올려주시면 됩니다. 



## SQL_ADVANCED_3rd

### 14.20.2 Window Function Concepts and Syntax

### 14.20.1 Window Function Description

### 14.19.1 Aggregate Function Descriptions

- 위 문서 중 *14.19.1. Aggregate Function Descriptions* 문서에서 1주차 (집계 함수) 에서 다룬 부분을 제외하고 **OVER( ) 절을 활용한 윈도우 함수 문법과 `RANK( ), DENSE_RANK( ), ROW_NUMBER( ), LAG( ), LEAD( )`등 윈도우 함수 특유의 기능 중심으로 정리해주세요.**



## 🏁 강의 수강 (Study Schedule)

| 주차  | 공부 범위               | 완료 여부 |
| ----- | ----------------------- | --------- |
| 1주차 | 서브쿼리 & CTE          | ✅         |
| 2주차 | 집합 연산자 & 그룹 함수 | ✅         |
| 3주차 | 윈도우 함수             | ✅         |
| 4주차 | Top N 쿼리              | 🍽️         |
| 5주차 | 계층형 질의와 셀프 조인 | 🍽️         |
| 6주차 | PIVOT / UNPIVOT         | 🍽️         |
| 7주차 | 정규 표현식             | 🍽️         |



### 공식 문서 활용 팁

>  **MySQL 공식 문서는 영어로 제공되지만, 크롬 브라우저에서 공식 문서를 열고 이 페이지 번역하기에서 한국어를 선택하면 번역된 버전으로 확인할 수 있습니다. 다만, 번역본은 문맥이 어색한 부분이 종종 있으니 영어 원문과 한국어 번역본을 왔다 갔다 하며 확인하거나, 교육팀장의 정리 예시를 참고하셔도 괜찮습니다.**



# 1️⃣ 학습 내용

> 아래의 링크를 통해 *MySQL 공식문서*로 이동하실 수 있습니다.
>
> - 14.20.2 Window Function Concepts and Syntax : MySQL 공식문서
>
> https://dev.mysql.com/doc/refman/8.0/en/window-functions-usage.html
>
> (한국어 버전) https://dart-b-official.github.io/posts/mysql-Window-Function/
>
> - 14.20.1 Window Function Description : MySQL 공식문서
>
> https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html
>
> (한국어 버전) https://dart-b-official.github.io/posts/mysql-Window-Function(2)/
>
> - 14.19.1 Aggregate Function Descriptions : MySQL 공식문서
>
> https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html
>
> (한국어 버전) https://dart-b-official.github.io/posts/mysql-aggregate_function/
>

<br>



---

# 2️⃣ 학습 내용 정리하기

## 1. 윈도우 함수

~~~
✅ 학습 목표 :
* OVER 절을 통해 행 단위 분석을 가능하게 하는 윈도우 함수의 구조를 이해한다.
* RANK, DENSE_RANK, ROW_NUMBER의 차이를 구분하고 사용할 수 있다.
* 이전 또는 이후 행을 참조하는 LAG, LEAD 함수를 적절히 사용할 수 있다.
~~~

### <윈도 함수 기본 개념>
* 집계 함수: 여러 행을 하나의 결과 행으로 축소 (예: SUM(profit) → 전체 합계)   
* 윈도 함수: 각 행마다 결과를 반환 (집계와 유사하지만 “행 단위”)   
* 현재 행(Current row): 함수 계산이 수행되는 대상 행   
* 윈도(Window): 현재 행을 기준으로 관련된 행들의 집합

ex)   
```sql
SELECT
  year, country, product, profit,
  SUM(profit) OVER() AS total_profit,
  SUM(profit) OVER(PARTITION BY country) AS country_profit
FROM sales
ORDER BY country, year, product, profit;
```

### <사용 위치와 실행 순서>   
* 윈도 함수는 SELECT 목록과 ORDER BY 절에서만 사용 가능
* 실행 순서: FROM → WHERE → GROUP BY → HAVING → (윈도 함수) → ORDER BY → LIMIT

### over절 문법   
```sql
over_clause:
    {OVER (window_spec) | OVER window_name}
```
### 윈도함수 목록   
#### CUME_DIST() over_clause
* 파티션 내 현재 행 값 이하의 비율(누적분포) 반환. 범위: 0 ~ 1.   
* ORDER BY 권장: 없으면 모든 행이 피어로 간주되어 값은 N/N = 1(N=파티션 크기).


#### DENSE_RANK() over_clause
* 파티션 내 순위를 반환하되 동점 간격이 생기지 않도록 연속 순위 부여.   
* ORDER BY 권장(없으면 모두 피어).

#### FIRST_VALUE(expr) [null_treatment] over_clause
* 프레임 첫 행의 expr 값을 반환.   
* 프레임 정의에 따라 결과가 달라짐(예: ROWS UNBOUNDED PRECEDING 등).

#### LAG(expr [, N[, default]]) [null_treatment] over_clause
* 파티션에서 현재 행 기준 N행 이전의 expr 값을 반환.   
* 해당 행이 없으면 default 반환. 기본값: N=1, default=NULL.
* 제약
       * N은 0 ~ 2^63 범위의 비음수 정수 리터럴/파라미터/변수여야 함.   
       * N은 NULL일 수 없음. N=0이면 현재 행의 expr.
#### LAST_VALUE(expr) [null_treatment] over_clause   
* 프레임 마지막 행의 expr 값을 반환.   
* 프레임/정렬 정의에 따라 값이 달라집니다(→ FIRST_VALUE() 예시 참고).

#### LEAD(expr [, N[, default]]) [null_treatment] over_clause   
* 파티션에서 현재 행 기준 N행 이후의 expr 값을 반환.   
* 해당 행이 없으면 default 반환. 기본값: N=1, default=NULL.

#### NTH_VALUE(expr, N) [from_first_last] [null_treatment] over_clause
* 프레임 N번째 행의 expr 값을 반환. 없으면 NULL.   
* N은 양의 정수 리터럴이어야 함.   
* from_first_last(표준): MySQL은 FROM FIRST만 허용(기본).   
* FROM LAST는 파싱되나 오류. 같은 효과를 내려면 내림차순 ORDER BY로 프레임을 뒤집어 구현.

#### NTILE(N) over_clause
* 파티션을 N개 버킷으로 분할 후, 현재 행의 버킷 번호(1~N) 반환.   
* N은 양의 정수 리터럴.

#### PERCENT_RANK() over_clause
* 파티션 내 최대값을 제외한 값 기준 상대 백분위 순위 반환.   
* 공식: (rank - 1) / (rows - 1) (0~1).   
* ORDER BY 권장

#### RANK() over_clause   
* 파티션 내 순위를 반환하되, 동점 시 같은 순위를 부여하며 간격(gaps) 발생.
* ORDER BY 권장.

#### ROW_NUMBER() over_clause
* 파티션 내 현재 행의 일련번호(1 ~ 파티션 행수) 반환.   
* ORDER BY가 번호 부여 순서를 결정. 없으면 비결정적.   
* 동점에 서로 다른 번호를 부여. 동점에 동일 값을 원하면 RANK()/DENSE_RANK() 사용.

### 집계함수    
* AVG() :인자의 평균값 반환
* BIT_AND() : 비트 AND 반환
* BIT_OR() :비트 OR 반환
* BIT_XOR() :비트 XOR 반환
* COUNT(): 반환된 행 수 반환
* COUNT(DISTINCT): 서로 다른 값의 개수 반환
* GROUP_CONCAT(): 문자열 연결 결과 반환
* JSON_ARRAYAGG() :결과 집합을 단일 JSON 배열로 집계
* JSON_OBJECTAGG() : 결과 집합을 단일 JSON 객체로 집계

<시간형(temporal) 주의>   
SUM(), AVG()는 시간형에 직접 동작하지 않습니다(숫자로 변환되어 비의도적 손실)   

---

# 3️⃣ 실습 문제

## LeetCode 문제 

https://leetcode.com/problems/department-top-three-salaries/

> LeetCode 185. Department Top Three Salaries 
>
> 학습 포인트 : DENSE_RANK( ) + PARTITION BY 사용으로 그룹 내 상위 N개 추출

https://leetcode.com/problems/consecutive-numbers/

> LeetCode 180. Consecutive Numbers 
>
> 학습 포인트 : LAG( ) 함수로 이전 값과 비교하여 연속 데이터 탐지 

https://leetcode.com/problems/last-person-to-fit-in-the-bus/

> LeetCode 2481. Last Person to Fit in the Bus 
>
> 학습 포인트 : SUM( ) OVER (ORDER BY ...) 로 누적 합계 계산 후 조건 필터링 



문제를 푸는 다양한 방법이 존재하지만, **윈도우 함수를 사용하여 해결하는 방식에 대해 고민해주시길 바랍니다.** 

---

## 문제 인증란

<!-- 이 주석을 지우고 여기에 문제 푼 인증사진을 올려주세요. -->



---

# 확인문제

## 문제 1

> **🧚예린이는 고객별로 얼마나 많은 주문을 하는지 분석하기 위해, 고객의 주문 목록에 주문 순서를 표시하는 쿼리를 작성해보았습니다. 이때 주문일 순서대로 각 고객의 주문 번호를 매기기 위해 윈도우 함수를 활용했습니다.**

~~~sql
SELECT customer_id, order_id, order_date,
       ROW_NUMBER() OVER (PARTITION BY customer_id ORDER BY order_date) AS order_rank
FROM Orders;
~~~

> **이번에는 예린이에게 "윈도우 함수를 쓰지 않고 동일한 결과를 만들어보라"는 미션을 받았습니다. 예린이는 이 작업을 어떻게 해야할지 막막합니다. 예린이를 도와 ROW_NUMBER() 윈도우 함수 없이 동일한 결과를 서브쿼리나 JOIN을 사용해서 작성해보세요.**

~~~
여기에 답을 작성해주세요!
~~~



<br>

### 🎉 수고하셨습니다.
