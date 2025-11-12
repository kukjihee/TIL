# SQL_ADVANCED 7주차 정규 과제

## Week 7 : 정규 표현식 (REGEXP)

📌**SQL_ADVANCED 정규과제**는 매주 정해진 주제에 따라 **MySQL 공식 문서 또는 한글 블로그 자료를 참고해 개념을 정리한 후, 프로그래머스 SQL 문제 3문제**와 **추가 확인문제**를 직접 풀어보며 학습하는 과제입니다.

이번 주는 아래의 **SQL_ADVANCED_7th_TIL**에 나열된 주제를 중심으로 개념을 학습하고, 주차별 **학습 목표**에 맞게 정리해주세요. 정리한 내용은 GitHub에 업로드한 후, **스프레드시트의 ‘SQL’ 시트에 링크를 제출**해주세요.

**(수행 인증샷은 필수입니다.)**

> 프로그래머스 문제를 풀고 ‘정답입니다’ 문구를 캡쳐해서 올려주시면 됩니다.

**(마지막 주차입니다. 조금만 더 힘내주세요~!!!)**

## **SQL_ADVANCED_7th_TIL**

### 14.8.2 Regular Expressions

- **REGEXP/RLIKE 연산자와 REGEXP_LIKE(), REGEXP_REPLACE() 등 함수 사용법 및 정규표현식 패턴 문법을 학습하세요.**



## **🏁 강의 수강 (Study Schedule)**

| **주차** | **공부 범위**           | **완료 여부** |
| -------- | ----------------------- | ------------- |
| 1주차    | 서브쿼리 & CTE          | ✅             |
| 2주차    | 집합 연산자 & 그룹 함수 | ✅             |
| 3주차    | 윈도우 함수             | ✅             |
| 4주차    | Top N 쿼리              | ✅             |
| 5주차    | 계층형 질의 & 셀프 조인 | ✅             |
| 6주차    | PIVOT / UNPIVOT         | ✅             |
| 7주차    | 정규 표현식             | ✅             |

### 공식 문서 활용 팁

>  **MySQL 공식 문서는 영어로 제공되지만, 크롬 브라우저에서 공식 문서를 열고 이 페이지 번역하기에서 한국어를 선택하면 번역된 버전으로 확인할 수 있습니다. 다만, 번역본은 문맥이 어색한 부분이 종종 있으니 영어 원문과 한국어 번역본을 왔다 갔다 하며 확인하거나, 교육팀장의 정리 예시를 참고하셔도 괜찮습니다.**



# 1️⃣ 학습 내용

> 아래의 링크를 통해 *MySQL 공식문서*로 이동하실 수 있습니다.
>
> - 14.8.2 Regular Expressions : MySQL 공식문서 
>
> https://dev.mysql.com/doc/refman/8.0/en/regexp.html
>
> (한국어 버전)



<br>

---

# 2️⃣ 학습 내용 정리하기

## 1. 정규 표현식 REGEXP

```
✅ 학습 목표 :
* `REGEXP`, `REGEXP_LIKE` 등으로 문자열 패턴 검색을 수행할 수 있다.
* `^`, `$`, `[abc]`, `.` 등 기본적인 정규표현식 패턴을 이해하고 WHERE절에 활용할 수 있다.
* 데이터 정제 및 분류 조건을 문자열 기반으로 처리할 수 있다.
```

* REGEXP: 문자열에서 특정 패턴을 검색하거나 치환하는 기능
* 기본 패턴 기호
  - ^ : 문자열 시작
  - $ : 문자열 끝
  - . : 모든 문자
  - * : 0회 이상 반복
  - + : 1회 이상 반복
  - ? : 0 또는 1회
  - {m,n} : 반복 횟수 지정
  - [abc] : a, b, c 중 하나
  - [^abc] : a, b, c를 제외한 문자
  - | : OR (선택)
  - (abc) : 그룹화

* 정규식으로 단순 비교를 넘어 패턴 기반 검색·추출·치환 가능

* 데이터 정제, 필터링, 검증 등 문자열 처리 효율 향상

* REGEXP_LIKE를 중심으로 다양한 문자열 조건 구현 가능

<br>

---

# 3️⃣ 실습 문제

## 문제

- https://leetcode.com/problems/find-users-with-valid-e-mails/description/

> LeetCode 1517. Find Users With Valid E-mails
>
> 학습 포인트 : REGEXP를 활용한 이메일 유효성 검사 

- https://leetcode.com/problems/employees-with-missing-information/description/

> LeetCode 1965. Employees With Missing Information
>
> 학습 포인트 : REGEXP를 이용해 NULL 이 아닌 빈 문자열, 공백 등 이상값을 감지하기

**물론 REGEXP 없이 풀 수 있는 문제입니다. 하지만, 정규 표현식을 학습 한 만큼, 최대한 정규 표현식을 활용해서 문제를 풀어주세요**.

(아래는 그동안 배운 내용들을 토대로 풀어보세요.)

- https://school.programmers.co.kr/learn/courses/30/lessons/59413

> 입양 시각 구하기 (2)

- https://school.programmers.co.kr/learn/courses/30/lessons/299305

> 대장균들의 자식의 수 구하기

- https://school.programmers.co.kr/learn/courses/30/lessons/131534

> 상품을 구매한 회원 비율 구하기



---

## 문제 인증란

<img width="727" height="538" alt="화면 캡처 2025-11-12 122341" src="https://github.com/user-attachments/assets/de0d0bd7-0e2c-465f-abcf-67b497b9e670" />   
<img width="757" height="473" alt="2" src="https://github.com/user-attachments/assets/e5d79795-cf87-4020-a203-7397588a1376" />   
<img width="909" height="397" alt="3" src="https://github.com/user-attachments/assets/c094564b-04c6-45ee-841d-d191113ec47a" />   
<img width="925" height="382" alt="4" src="https://github.com/user-attachments/assets/11a2d46c-0b9d-4eee-993e-c3334138b85a" />   
<img width="922" height="383" alt="5" src="https://github.com/user-attachments/assets/71585be8-f2ba-43ff-a2ff-2043796e739c" />






---

## 확인문제

### 문제 1

> **🧚희주는 고객의 이메일을 필터링하는 작업을 하고 있습니다. 모든 고객 중 이메일 도메인이 @gmail.com 또는 @naver.com인 고객만 추출하고자 합니다. REGEXP를 활용하여 쿼리를 작성해보세요.**

```
SELECT *
FROM customers
WHERE email REGEXP '(@gmail\\.com|@naver\\.com)$';
```

1. >
@gmail\\.com 또는 @naver\\.com 으로 끝나는 문자열($) 을 찾는다.

| → OR 조건

\\. → 정규식에서 .은 모든 문자이므로, 실제 마침표(.)를 의미하려면 \\.로 escape 필요

즉, 이메일이 @gmail.com 이거나 @naver.com 으로 끝나는 고객만 조회


=> 
```sql
SELECT *
FROM customers
WHERE email LIKE '%@gmail.com'
   OR email LIKE '%@naver.com';
```

2. > 
```sql
SELECT *
FROM customers
WHERE email IS NOT NULL
  AND email <> ''
  AND (email REGEXP '(@gmail\\.com|@naver\\.com)$');
```



### 문제 2

> **🧚운영팀장인 지민이는 학회원 데이터에서 핸드폰 번호 형식을 점검하는 업무를 맡았습니다. 핸드폰 번호는 반드시 010으로 시작하고, 중간과 끝은 각각 4자리 숫자로 구성되어야 하며, 각 구간은 하이픈(-)으로 구분되어야 합니다. 예: 010-1234-5678 **
>
> **올바른 형식을 따르지 않는 번호를 가진 고객 목록을 찾아내기 위해 SQL의 REGEXP 기능을 사용하려고 합니다. 아래 조건에 맞는 고객 목록을 출력하는 쿼리를 작성해주세요.**

- 예시 테이블

| **student_id** | **name** | **phone_number** |
| -------------- | -------- | ---------------- |
| 1              | Anna     | 010-1234-5678    |
| 2              | Brian    | 011-1234-5678    |
| 3              | Cindy    | 01012345678      |
| 4              | David    | 010-123-5678     |
| 5              | Elsa     | 010-9999-8888    |

- 기대 출력 결과

| **student_id** | **name** | **phone_number** |
| -------------- | -------- | ---------------- |
| 2              | Brian    | 011-1234-5678    |
| 3              | Cindy    | 01012345678      |
| 4              | David    | 010-123-5678     |

> 문제 조건 
>
> - 형식이 **정확히** 010-XXXX-XXXX (X는 숫자, 총 4자리)인 경우만 통과
> - **정규 표현식을 사용하여 필터링**
> - 올바르지 않은 형식만 조회
> - 테이블 명은 Student로 해주세요.

~~~
SELECT *
FROM Student
WHERE phone_number NOT REGEXP '^010-[0-9]{4}-[0-9]{4}$';
~~~





<!-- SQL ADVANCED 과제가 마무리되었습니다. 본 과정은 실제 SQLD 자격시험의 2과목 (고급 SQL 문법)을 기반으로 커리큘럼을 구성했습니다. 따라서 이번 과제를 성실히 수행한 분들은 SQLD 자격증 취득에 도전해보는 것을 추천드립니다. 추가적으로 이번 과제로 끝나는 것이 아니라, 앞으로도 다양한 문제를 풀어보며 배운 내용을 꾸준히 복습하고 응용해 나가는 것이 중요합니다. 또한, MySQL 외에도 PostgreSQL, Oracle, SQLite 등 다양한 SQL 엔진을 학습하는 것도 추천드립니다. 각각의 데이터베이스는 문법과 기능에 조금씩 차이가 있지만, 기본적인 SQL 개념을 이해하고 있다면 훨씬 쉽게 적용하고 이해할 수 있을 것입니다. 앞으로의 SQL 공부에도 화이팅이고, 부족한 템플릿이지만 끝까지 함께해주셔서 진심으로 감사합니다. -->

### **🎉 수고하셨습니다.**
