### 6-2 가독성을 챙기기 위한 SQL 스타일 가이드    
#### 1. 예약어는 대문자로 작성   
EX)   
```sql   
SELECT   
col   
FROM table   
WHERE   
```   
#### 2. 컬럼 이름은 snake_case로 작성(일관성이 중요)   
#### 3. 명시적 VS 암시적인 이름   
   => Alias로 별칭을 지을 때는 명시적인 이름을 적용   
#### 4. 왼쪽 정렬   
#### 5. 예약어나 컬럼은 한 줄에 하나씩 권장   
EX)   
```sql   
SELECT   
col1,   
col2,   
col3   
FROM table   
WHERE   
```   
#### 6. 쉼표는 컬럼 바로 뒤에   


### 6-3 가독성을 챙기기 위한 WITH 문 & 파티션      
#### WITH 구문   
: WITH 문을 사용해 쿼리를 정의해서 재사용 가능   
```sql   
SELECT   
col, col2   
FROM (   
    SELECT   
    col,col2,col3 ...   
    FROM   
    Table   
)   
```   
이렇게 말고   
```sql   
WITH temp_table AS(   
    SELECT   
    col,col2,col3 ...   
    FROM   
    Table   
)   
SELECT   
col,col2   
FROM temp_table   
```   
WITH문 사용해서 가독성 올리기(매우 유용)   

#### <WITH 구문>   
* CTE(Common Table Expression)   
* SELECT 구문에 이름을 정해주는 것과 유사   
* 쿼리 내에서 반복적으로 사용할 수 있음   
* 사용 방법   
```sql   
WITH name_a AS(   
    SELECT   
    col   
    FROM Table   
), name_b AS(   
    SELECT   
    col2   
    FROM Table2   
)   
SELECT   
col   
FROM name_a   
```   
   
#### PARTITION   
##### <장점>   
1) 쿼리 성능 향상   
   - 전체 데이터를 스캔하는 것보다 파티션을 설정한 곳만 스캔하는 것이 더 빠름   
2) 데이터 관리 용이성   
   - 특정 일자의 데이터를 모두 변경하거나 삭제해야 하면 파티션을 설정해서 삭제할 수 있음   
3) 비용   
   - 파티션에 해당하는 데이터만 스캔해서 비용을 줄일 수 있음   
(BigQuery는 쿼리 용량에 비례해서 과금)   

### 6-4 데이터 결과 검증 정의     
 : SQL 쿼리 후 얻은 결과가 예상과 일치하는지 확인하는 과정   
 * 목적: 분석 결과의 정확성, 신뢰성 확보   
 * 문제를 잘 정의하고, 미리 작성해보기   
 * 도메인 특수성 잘 파악하기   
 * 내가 기대하는 예상결과를 정의하고 쿼리 작성 후 두개가 일치하는지 비교   
   
#### 데이터 결과를 검증하는 흐름   
1) 문제 정의 확인   
   * 구체적인 문제 정의   
   * 요청사항도 구체적으로 확인   
2) Input/Output   
   * 데이터의 Input과 (원하는 형태의) Output 작성하기   
   * "Input - (중간결과) - Output"에서 중간 결과 생각하기   
3) 쿼리 작성   
   * 가독성 챙기기   
4) 결과 비교   
   * 예상과 실제 쿼리 결과의 차이가 있는지 확인   
5) 끝   
   * 오류가 없다면 끝   
   * 오류가 있다면 다시 쿼리 작성   


### 6-5 데이터 결과 검증 예시     
 
### 6-6 정리   

