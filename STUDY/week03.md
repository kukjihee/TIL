
### 내문제 

``sql``  
SELECT   
  A.APNT_NO,   
  P.PT_NAME,   
  P.PT_NO,   
  A.MCDP_CD,   
  D.DR_NAME,   
  A.APNT_YMD   
FROM APPOINTMENT A   
JOIN PATIENT P ON A.PT_NO = P.PT_NO #환자이름 가져오기    
JOIN DOCTOR D ON A.MDDR_ID = D.DR_ID #의사이름 가져오기    
WHERE A.APNT_CNCL_YN = 'N' #예약취소되지 않은 것만   
  AND A.MCDP_CD = 'CS' #흉부외과만   
  AND A.APNT_YMD BETWEEN '2022-04-13 00:00:00' AND '2022-04-13 23:59:59' #4/13일 하루    
ORDER BY A.APNT_YMD;   

### 민주님 문제 

``sql``    
SELECT   
  ID,   
  EMAIL,   
  FIRST_NAME,   
  LAST_NAME   
FROM DEVELOPERS   
WHERE SKILL_CODE & 256 > 0      
OR SKILL_CODE & 1024 > 0   
ORDER BY ID;   


### 승화님 문제 

``sql``   
SELECT    
  E.ID,   
  COUNT(C.ID) AS CHILD_COUNT #자식 없으면 0으로 처리    
FROM ECOLI_DATA E   
LEFT JOIN ECOLI_DATA C #자식없는 개체도 무조건 포함되게 하려고 left join 사용    
  ON E.ID = C.PARENT_ID   
GROUP BY E.ID   
ORDER BY E.ID;   
