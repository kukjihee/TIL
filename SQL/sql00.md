1-1 BigQuery 기초 지식
OLTP : 거래를 하기 위해 사용되는 데이터베이스 => 서비스에서 많이 사용
OLAP
BigQuery : SQL 사용해 쉽게 데이터 추출 가능/ OLAP 도구이므로 속도가 빠름/ 구글에서 인프라 관리
 -비용 
SQL : 데이터베이스에서 데이터를 가지고 올 때 사용

1-2 BigQuery 환경 설정
구성요소 
1) 프로젝트 : 하나의 프로젝트에 여러 데이터셋이 존재 가능
2) 데이터셋 : 프로젝트에 있는 창고/ 판매 데이터 등 별도의 데이터 저장 가능
3) 테이블 : 창고에 있는 선반

2-1 데이터 활용 Overview
데이터 활용 과정
어떤 일을 해야한다 -> 원하는 것을 정한다(문제정의+지표정의)
-> 데이터 탐색(단일자료, 다량의 자료 -> 조건,추출,변환,요약) -> 데이터 결과 검증 -> 피드백/활용

2-2 저장된 데이터 확인하기(데이터베이스, 데이터 웨어하우스, ERD)
- 구체적인 문제정의하면서 쿼리 작성
- 회사에 존재할 수 있는 데이터 예시
  1) 서비스에 사용될 데이터베이스 : 유저 테이블/배송 테이블/물건 테이블
  2) 앱/웹 로그 데이터 : 유저가 앱/웹에 들어와서 회원 가입-> 페이지 확인, 컨텐츠 확인 등등의 데이터(user flow 기록)
                      / '과정'을 알 수 있는 데이터
  3) 공공데이터, 서드파티 데이터 : 날씨/ 페이스북 광고 데이터
 
  
   

느낀점: 
SQL은 데이터 추출과 분석의 도구로 대용량 데이터를 효율적으로 처리할 수 있으며 특히 금융권 및 데이터 직무에서는 필수적인 기술이라고 느꼈다.
SQLD 자격증을 따기 위해 공부했던 개념이 당연하게 쓰이기에 듣기에는 익숙한 기분이 들었지만, BigQuery를 사용함에 있어 굉장히 어색하고 영상을 따라감에 어려움을 느꼈다. 과제를 수행해 나가며 점차 익숙해져가는 모습을 기대하게 된다.




  <img width="515" alt="SQL 00" src="https://github.com/user-attachments/assets/4e56f9d2-58dd-428e-bcb5-1266b592ae7e" />
