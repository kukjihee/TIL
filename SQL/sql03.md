##  3-4 오류를 디버깅하는 방법  
오류: 부정확하거나 잘못된 행동을 의미 

오류메세지 검색해서 오류 해결하기    

## 4-2 데이터 타입과 데이터 변환(CAST, SAFE_CAST)   

SELECT 
컬럼1,   
컬럼2,   
컬럼3   
FROM 테이블   
WHERE <조건문>   
GROUP BY <집계할 컬럼>   

* SELECT문에서 데이터를 변환시킬 수 있음   
또는 WHERE 조건문에도 사용할 수 있음   
   
* 데이터타입: 숫자, 문자, 시간/날짜, BOOL, ...   

#### <자료 타입 변경하기>   
* 자료 타입을 변경하는 함수: CAST   

SELECT   
CAST(1 AS string) #숫자 1을 문자 1로 변경   

만약,   
SELECT   
CAST("카일스쿨" AS INT64) #문자열을 숫자형으로?  -> 오류 발생   

* 더 안전하게 데이터 타입 변경하기: SAFE_CAST   
SAFE_가 붙은 함수는 변환이 실패할 경우 NULL 반환   





## 4-3 문자열 함수(CONCAT, SPLIT, REPLACE, TRIM, UPPER)   
- 문자열 붙이기   
- 문자열 분리하기   
- 특정 단어 수정하기   
- 문자열 자르기   
- 영어 대문자 변환    
### 1. CONCAT   
: 문자열 붙이기

SELECT   
CONCAT("안녕","하세요","!") AS result   
--FROM이 없는데 어떻게 동작하지?   
--CONCAT 인자로 STRING이나 숫자를 넣을 때는 데이터를 직접 넣어준 것 => FROM이 없어도 실행  

### 2. SPLIT
: 문자열 분리하기(쪼개다)     

SELECT   
SPLIT("가,나,다,라",", ") AS result   
--SPLIT(문자열_원본, 나눌 기준이 되는 문장)


### 3. REPLACE   
:특정 단어 수정하기   

SELECT    
REPLACE("안녕하세요","안녕","실천") AS result   
--REPLACE(문자열 원본, 찾을 단어, 바꿀 단어)


### 4. TRIM   
: 문자열 자르기   

SELECT   
TRIM("안녕하세요","하세요") AS result   
-- TRIM(문자열 원본, 자를 단어)   

### 5. UPPER   
: 영어 소문자를 대문자로 변경   

SELECT   
UPPER("abc") AS result   
--UPPER(문자열 원본)   

## 4-4 날짜 및 시간 데이터 이해하기(1) (타임존, UTC, Millisecond, TIMESTAMP/DATETIME)   

1.  날짜 및 시간 데이터 타입 파악하기: DATE, DATETIME, TIMESTAMP   
2. 날짜 및 시간 데이터 관련 알면 좋은 내용: UTC, Millisecond   
3. 날짜 및 시간 데이터 타입 변환하기   
4. 시간함수(두 시간의 차이, 특정 부분 추출하기)   

#### < 시간 데이터 >   
* DATE: DATE만 표시하는 데이터, 2025-04-05   
* DATERIME: DATE와 TIME까지 표시하는 데이터, TimeZone 정보없음, 2025-04-05 14:00:00   
* TIME: 날짜와 무관하게 시간만 표시하는 데이터, 23:59:59.00   

#### <타임존>   
* GMT: 영국의 그리니치 천문대를 기준으로 지역에 따른 시간의 차이를 조정하기 위해 생긴 시간의 구분선 (한국시간: GMT + 9)   

* UTC: 국제적인 표준시간 ( 한국시간: UTC +9 )   

* TIMESTAMP: UTC부터 경과한 시간을 나타내는 값 (TimeZone 정보 있음), 2025-04-05 14:00:00 UTC   

#### < 시간 데이터 다루기>   
* millisecond(ms)   
천분의 1초... 빠른 반응이 필요한 분야에서 사용   
보통 millisecond -> TIMESTAMP -> DATETIME 로 변환해서 사용    


#### < TIMESTAMP vs DATETIME >   
* TIMESTAMP: UTC 라고 나옴/ 한국 시간 -9시간   
* DATETIME: T가 나옴/ 한국 ZONE 사용시 한국 시간과 동일   
CURRENT_TIMESTAMP() AS timestamp_col   
DATETIME(CURRENT_TIMESTAMP(), 'AISA/SEOUL') AS datetime_col

<img width="616" alt="화면 캡처 2025-04-05 182404" src="https://github.com/user-attachments/assets/9d5629e7-e3d4-4c5f-88ee-247b364486a9" />

