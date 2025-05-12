## 5-2 JOIN 이해하기   
Join: 다량의 자료 - 연결   
=> 서로 다른 데이터 테이블을 연결하는 것   
=> 공통적으로 존재하는 컬럼(=Key)이 있다면, JOIN 할 수 있음   

EX) 트레이너가 포획한 포켓몬 기준으로 트레이너 데이터를 연결(JOIN)   
* 연결할 수 있는 Key = trainer_id, id  (두개 모두 트레이너 아이디를 의미)    

 <JOIN을 해야하는 이유>   
 for 데이터 저장되는 형태에 대한 이해   
 * 데이터 분석하는 관점에서는 미리 JOIN되어 있는 것이 좋음   

   

## 5-3 다양한 JOIN(LEFT, RIGHT, INNER, CROSS JOIN)   
* (INNER) JOIN   
* LEFT/RIGHT (OUTER) JOIN   
* FULL (OUTER) JOIN   
* CROSS JOIN
  
<img width="594" alt="화면 캡처 2025-05-12 133439" src="https://github.com/user-attachments/assets/401648ad-8bf5-4e09-91b3-277fdf47ff51" />   



## 5-4 JOIN 쿼리 작성하기   
1. 테이블 확인: 테이블에 저장된 데이터, 컬럼 확인   
2. 기준 테이블 정의: 가장 많이 참고할 기준(base)테이블 정의   
3. JOIN Key 찾기: 여러 Table과 연결할 Key(ON) 정리   
4. 결과 예상하기: 결과 테이블을 예상, 손/엑셀로 작성   
5. 쿼리 작성/검증: 예상한 결과와 동일한 결과가 나오는지 확인   
   
```sql   
SELECT   
A.col1,   
A.col2,   
B.col1 1,   
B.col2 2   
FROM table1 AS A   
LEFT JOIN table2 AS B   
ON A.key = B.key #Alias(별칭)사용 가능   
```   
* CROSS JOIN은 ON 쓸 필요 없음   

EX)    
* LEFT: trainer_pokemon   
* RIGHT: trainer   
* RIGHT: pokemon   

```sql   
SELECT   
tp.*,   
t.*,   
p.*   
#아니면   
#tp.*,   
#t.*EXCEPT(id)   
#p.*EXCEPT(id)   
#tp에 id있으니 중복되니까 제외   
FROM basic.trainer_pokemon AS tp   
LEFT JOIN basic.trainer.t   
ON tp.trainer_id = t.id   
LEFT JOIN basic.pokemon AS p   
ON tp.pokemon_id = p.id  #JOIN key 입력    
```   

## 5-5 JOIN을 처음 공부할 때 헷갈렸던 부분   
* 하려고 하는 "작업의 목적"에 따라   
* JOIN의 개수에 한계는 없음   
