## 4-4   
### DATETIME 함수   
#### 1) CURRENT_DATETIME : 현재 DATETIME 출력      

```sql 
select   
current_date() as current_date,   
current_date("Asia/Seoul") as asia_date,   
current_datetime() as current_datetime,   
surrent_datetime("Aisa/Seoul") as current_datetime_asia;   
``` 
#### 2) EXTRACT : DATETIME에서 특정 부분만 추출하고 싶은 경우      

```sql   
select   
extract(DATE FROM DATETIME "2024-01-02 14:00:00") AS date,   
extract(YEAR FROM DATETIME "2024-01-02 14:00:00") AS year,    
extract(MONTH FROM DATETIME "2024-01-02 14:00:00" AS DATETIME) AS month,    
extract(DAY FROM DATETIME "2024-01-02 14:00:00" AS DATETIME) AS day,    
extract(HOUR FROM DATETIME "2024-01-02 14:00:00" AS DATETIME) AS hour,   
extract(MINUTE FROM DATETIME "2024-01-02 14:00:00" AS DATETIME) AS minute,       
extract(DAYOFWEEK FROM DATETIME_col) #요일을 추출. 한주의 첫날이 일요일인 [1.7] 범위로 반환    
```    
   
#### 3) DATETIME_TRUNC   
: DATE와 HOUR만 남기고 싶은 경우 -> 시간자르기   
```sql   
datetime_trunc(datetime_col, HOUR)    
```   
"2024-01-02 14:42:13"을 HOUR 로 자르면   
"2024-01-02 14:00:00" 반환    

#### 4) PARSE_DATETIME   
: 문자열로 지정된 DATETIME을 DATETIME 타입으로 바꾸꼬 싶은 경우   
```sql   
select   
parse_datetime('%Y-%m-%d %H:%M:%S' ,'2024-01-11 12:35:35') as parse_datetime;   
```   
#### 5) LAST_DAY   
: 마지막 날을 알고 싶은 경우/ 자동으로 월의 마지막 값을 계산해서 특정 연산을 할 경우   
```sql   
select   
Last_day(DATETIME '2024-01-03 15:30:00') AS last_day,   
Last_day(DATETIME '2024-01-03 15:30:00'MONTH) AS last_day_month,   
Last_day(DATETIME '2024-01-03 15:30:00' WEEK) AS last_day_week,   
Last_day(DATETIME '2024-01-03 15:30:00'WEEK(SUNDAY)) AS last_day_week_sun,   #일요일기준 마지막날   
Last_day(DATETIME '2024-01-03 15:30:00'WEEK(MONDAY)) AS last_day_week_mon   #월요일기준 마지막날   
```   
   
#### 6) DATETIME_DIFF   
: 두 DATETIME의 차이를 알고 싶은 경우   
```sql   
select   
datetime_diff(first_datetime, second_datetime, DAY) as day_diff1,   
datetime_diff(second_datetime, first_datetime, DAY) as day_diff2,     
datetime_diff(first_datetime, second_datetime, MONTH) as month_diff1,   
datetime_diff(first_datetime, second_datetime, WEEK) as week_diff1,     
FROM(     
SELECT   
DATETIME "2024-04-02 10:20:00" AS first_datetime,     
DATETIME "2021-01-01 15:30:00" AS second_datetime,   
)   
```   

