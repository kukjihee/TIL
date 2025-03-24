2-6 연습문제   
NULL: 아무것도 없는값, 값이 존재하지 않을 때 NULL   
-> 0과 **과는 다름   
WHere 절에서 여러 조건을 연결하고 싶은 경우   
  -> AND 조건을 사용      
  -> () OR ()    


집계함수는 GROUP BY 와 같이 다님. 집계하는 기준(컬럼)이 없으면 COUNT만 쓸 수 있으나, 집계하는 기준이 있다면 그 기준 컬럼을 GROUP BY에 써줘야 함.     
DISTINCT: 고유한 값만 보고 싶을 때 사용. UNIQUE한 값만 알고 싶은 경우 사용  
ex) COUNT(DISTINCT user_id) AS dau -> 이런 데이터를 저장하는 곳에 접속 기록, 이벤트 로그가 여러 ROW 존재 => UNIQUE => DISTINCT   

