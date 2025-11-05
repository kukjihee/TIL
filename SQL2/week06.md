# SQL_ADVANCED 6주차 정규 과제

## **Week 6 : PIVOT / UNPIVOT**

📌**SQL_ADVANCED 정규과제**는 매주 정해진 주제에 따라 **MySQL 공식 문서 또는 한글 블로그 자료를 참고해 개념을 정리한 후, 프로그래머스 SQL 문제 3문제**와 **추가 확인문제**를 직접 풀어보며 학습하는 과제입니다.

이번 주는 아래의 **SQL_ADVANCED_6th_TIL**에 나열된 주제를 중심으로 개념을 학습하고, 주차별 **학습 목표**에 맞게 정리해주세요. 정리한 내용은 GitHub에 업로드한 후, **스프레드시트의 ‘SQL’ 시트에 링크를 제출**해주세요.

**(수행 인증샷은 필수입니다.)**

> 프로그래머스 문제를 풀고 ‘정답입니다’ 문구를 캡쳐해서 올려주시면 됩니다.

------

## **SQL_ADVANCED_6th_TIL**

- MySQL 공식문서에는 `PIVOT / UNPIVOT`에 대한 **전용 문법을 제공하지 않고 있습니다.** 따라서 이번 주차에서는 PIVOT / UNPIVOT에 대한 개념을 이해하고, 이를 `CASE WHEN + GROUP BY` 또는 `UNION ALL` 등의 조합으로 수동 구현할 수 있는 방법을 학습하면 됩니다. 



## **🏁 강의 수강 (Study Schedule)**

| **주차** | **공부 범위**           | **완료 여부** |
| -------- | ----------------------- | ------------- |
| 1주차    | 서브쿼리 & CTE          | ✅             |
| 2주차    | 집합 연산자 & 그룹 함수 | ✅             |
| 3주차    | 윈도우 함수             | ✅             |
| 4주차    | Top N 쿼리              | ✅             |
| 5주차    | 계층형 질의 & 셀프 조인 | ✅             |
| 6주차    | PIVOT / UNPIVOT         | ✅             |
| 7주차    | 정규 표현식             | 🍽️             |

<br>



# 1️⃣ 학습 내용

**참고할 자료를 아래에 같이 첨부합니다.**

<!-- 꼭 아래의 자료를 참고하지 않고, 개인적인 학습 방법으로 진행하셔도 좋습니다. -->

1. **PIVOT / UNPIVOT 개념 학습 Blog**

https://m.blog.naver.com/regenesis90/222205833002

https://blog.naver.com/regenesis90/222205964866

2. **MySQL 로 PIVOT 구현하기**

https://shxrecord.tistory.com/181



<br>

---

# 2️⃣ 학습 내용 정리하기

## 1. PIVOT

```
✅ 학습 목표 :
* MySQL에서 직접적인 `PIVOT` 문법은 없으므로, `CASE WHEN`, `GROUP BY`, `MAX()` 등으로 대체 구현할 수 있다.
* 데이터를 행 → 열 방향으로 전개하는 기본 로직을 이해한다.
```

* pivot table
  - 2가지 컬럼(X, Y)에 따라 그룹화되어 1개의 컬럼으로 표현된 집계함수 정보(K)를 X, Y 중 하나를 행렬전환하여, K값을 행과 열의 2차원적 정보로 조회할 수 있게 함.
    
  ```sql
  with temp as
    (select 컬럼이름X,
            컬럼이름Y,
            컬럼이름K
     from 테이블이름A)
  select * from temp
  pivot (
    집계함수(컬럼이름K) as 별명K
    for 컬럼이름Y in (컬럼X값1 as 별명X1,
                     컬럼X값2 as 별명X2,
                     ...)
  );
```



## 2. UNPIVOT

```
✅ 학습 목표 :
* UNPIVOT 역시 직접 문법이 없으므로, `UNION ALL`과 `JOIN`, JSON 등의 방법으로 열 → 행 형태로 변환하는 과정을 익힌다.
* `UNION ALL`로 수동 구현 시의 컬럼 이름 통일과 데이터 병합 과정을 익힌다.
```

* 그룹별로 집계된 집계함수 결과값이 각각 1개의 컬럼에 표시되는 경우가 UNPIVOT   
* ​UNPIVOT은 PIVOT의 반대 역할을 수행. 즉, 피벗 테이블을 해제하거나, 피벗 테이블 형식의 테이블을 그렇지 않은 형태로 만듦

```sql
select * from 테이블이름A
UNPIVOT (
컬럼이름K for 컬럼이름Y in (컬럼이름Y1_K as 컬럼Y값1,
                           컬럼이름Y2_K as 컬럼Y값2,
                           ...)
);
```



---

# 3️⃣ 실습 문제

## Leetcode 문제 

https://leetcode.com/problems/reformat-department-table/description/

> LeetCode. Reformat Department Table
>
> 학습 포인트 : MySQL 에서는 PIVOT을 쉽게 구할 수 있는 방법이 없다. 
>
> - 수동으로 구하기 : CASE WHEN + 집계함수 / GROUP BY + 조건 분기 사용



## 문제 인증란

```sql
SELECT
    id,
    SUM(CASE WHEN month = 'Jan' THEN revenue ELSE NULL END) AS Jan_Revenue,
    SUM(CASE WHEN month = 'Feb' THEN revenue ELSE NULL END) AS Feb_Revenue,
    SUM(CASE WHEN month = 'Mar' THEN revenue ELSE NULL END) AS Mar_Revenue,
    SUM(CASE WHEN month = 'Apr' THEN revenue ELSE NULL END) AS Apr_Revenue,
    SUM(CASE WHEN month = 'May' THEN revenue ELSE NULL END) AS May_Revenue,
    SUM(CASE WHEN month = 'Jun' THEN revenue ELSE NULL END) AS Jun_Revenue,
    SUM(CASE WHEN month = 'Jul' THEN revenue ELSE NULL END) AS Jul_Revenue,
    SUM(CASE WHEN month = 'Aug' THEN revenue ELSE NULL END) AS Aug_Revenue,
    SUM(CASE WHEN month = 'Sep' THEN revenue ELSE NULL END) AS Sep_Revenue,
    SUM(CASE WHEN month = 'Oct' THEN revenue ELSE NULL END) AS Oct_Revenue,
    SUM(CASE WHEN month = 'Nov' THEN revenue ELSE NULL END) AS Nov_Revenue,
    SUM(CASE WHEN month = 'Dec' THEN revenue ELSE NULL END) AS Dec_Revenue
FROM Department
GROUP BY id;
```

(컴퓨터 오류인지 문제 제출이 안돼서 코드라도 제출합니당..ㅠㅠ)

## 확인 문제 

### 문제 1

> **🧚지희는 매월 각 매장의 월별 매출 데이터가 담긴 테이블을 가공하려 합니다. 아래와 같은 테이블이 있다고 가정합시다.**

| **branch** | **Jan_sales** | **Feb_sales** | **Mar_sales** |
| ---------- | ------------- | ------------- | ------------- |
| A          | 100           | 120           | 130           |
| B          | 90            | 110           | 140           |

> **Q. 이 테이블을 아래와 같은 형태로 바꾸고 싶습니다. SQL에서 UNION ALL을 활용하여 UNPIVOT 구조를 수동으로 구현해보세요.**

| **branch** | **month** | **sales** |
| ---------- | --------- | --------- |
| A          | Jan       | 100       |
| A          | Feb       | 120       |
| A          | Mar       | 130       |
| B          | Jan       | 90        |
| B          | Feb       | 110       |
| B          | Mar       | 140       |

```
SELECT branch, 'Jan' AS month, Jan_sales AS sales
FROM sales_by_branch
UNION ALL
SELECT branch, 'Feb' AS month, Feb_sales AS sales
FROM sales_by_branch
UNION ALL
SELECT branch, 'Mar' AS month, Mar_sales AS sales
FROM sales_by_branch;

```



### 문제 2

> **🧚태연이는 지점별로 월별 매출을 한 눈에 보기 위해, 아래와 같이 매출 데이터가 저장된 데이터를 가공하려고 합니다.**

| **branch** | **month** | **sales** |
| ---------- | --------- | --------- |
| A          | Jan       | 100       |
| A          | Feb       | 120       |
| A          | Mar       | 130       |
| B          | Jan       | 90        |
| B          | Feb       | 110       |
| B          | Mar       | 140       |

> **이 데이터를 아래와 같이 월별 매출 컬럼이 각각 존재하도록 PIVOT 형태로 바꾸고 싶습니다.MySQL에서는 PIVOT 문법이 없기 때문에, CASE WHEN, GROUP BY, MAX() 또는 SUM() 등을 이용해 수동으로 구현해보세요.**

- 원하는 결과 

| **branch** | **Jan_sales** | **Feb_sales** | **Mar_sales** |
| ---------- | ------------- | ------------- | ------------- |
| A          | 100           | 120           | 130           |
| B          | 90            | 110           | 140           |

~~~
SELECT
    branch,
    SUM(CASE WHEN month = 'Jan' THEN sales END) AS Jan_sales,
    SUM(CASE WHEN month = 'Feb' THEN sales END) AS Feb_sales,
    SUM(CASE WHEN month = 'Mar' THEN sales END) AS Mar_sales
FROM branch_sales
GROUP BY branch;
~~~







### **🎉 수고하셨습니다.**
