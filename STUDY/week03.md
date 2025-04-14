
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

