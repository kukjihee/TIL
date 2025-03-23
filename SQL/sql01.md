2-3 데이터 탐색(SELECT,FROM,WHERE)   
SQL 쿼리문 문법   
1) SELECT: 테이블의 어떤 컬럼을 선택(출력)할 것인가?   
   col1 As new_name,   
   col2,   
   col3   
3) FROM dataset.table : 어떤 테이블에서 데이터를 확인할 것인가?   
4) WHERE: 만약 원하는 조건이 있다면 어떤 조건인가?   
   col1=1:조건문
   
* FROM : 데이터를 확인할 Table 명시. 이름이 너무 길다면 AS'별칭'으로 별칭 지정 가능.
  -> FROM Table AS t1
* WHERE : FROM에 명시된 Table에 저장된 데이터를 필터링(조건 설정). Table에 있는 컬럼을 조건 설정
* SELECT : Table에 저장되어 있는 컬럼 선택. 여러 컬럼 명시 가능.
  -> col1 AS '별칭'으로 컬럼의 이름도 별칭 지정 가능

2-5 집계(Group by+having+sum/count)
  SELECT
  집계할_컬럼1,
  집계 함수( count, max, min 등)
  ex) COUNT(DISTINCT count할 컬럼) AS col1_count    
  FROM Table
  GROUP BY
  집계할_컬럼1   
  HAVING   
  col1_count>3   

     
  *GROUP BY : 같은 값끼리 모아서 그룹화. 특정 컬럼을 기준으로 모으면서 다른 컬럼에선 집계 가능   
  -> 합, 평균, max, min 등   
  -> DISTINCT: Unique한 것만 보고 싶은 경우 사용(중복 제거)   
  -> 일자별 집계/ 연령대별 집계에 많이 이용   
*HAVING : GROUP BY한 후 조건을 설정하고 싶은 경우 사용     
*ORDER BY: 쿼리의 맨 마지막에 두고, 맨 마지막에 작성(DESC-내림차순, OSC-오름차순)      



[Where VS Having]    
Where: Table에 바로 조건을 설정하고 싶은 경우 사용      
Having: Group by한 후 조건을 설정하고 싶은 경우 사용         


   <img width="478" alt="화면 캡처 2025-03-23 224636" src="https://github.com/user-attachments/assets/77413c09-59e5-4443-8890-dc28074f19c9" />   

   
  
