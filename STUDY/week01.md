**#승화님문제   **   
    ```
    부모의 형질을 모두 보유한 대장균의 ID(ID), 대장균의 형질(GENOTYPE), 부모 대장균의 형질(PARENT_GENOTYPE)을 출력하는 SQL 문을 작성해주세요. 이때 결과는 ID에 대해 오름차순 정렬해주세요.
    ```

SELECT   
ID,   
GENOTYPE,   
PARENT_GENOTYPE   
FROM ECOLI_DATA   
WHERE ID="2"or"3"or"7"or"8"   
#부모의 형질을 모두 보유한 ID: 2,3,7,8   
ORDER BY ID

#어떻게 하는건지 모르겠답...ㅜㅜ   

   
      
**#유현님문제 **  
SELECT    
    DATE(o.order_purchase_timestamp) AS dt,   
    ROUND(SUM(p.payment_value), 2) AS revenue_daily   
FROM olist_orders_dataset o   
JOIN olist_order_payments_dataset p    
    ON o.order_id = p.order_id   
WHERE o.order_purchase_timestamp >= '2018-01-01'   
GROUP BY dt   
ORDER BY dt      

**
#민주님문제 **  
```
USED_GOODS_BOARD와 USED_GOODS_REPLY 테이블에서 2022년 10월에 작성된 게시글 제목, 게시글 ID, 댓글 ID, 댓글 작성자 ID, 댓글 내용, 댓글 작성일을 조회하는 SQL문을 작성해주세요. 결과는 댓글 작성일을 기준으로 오름차순 정렬해주시고, 댓글 작성일이 같다면 게시글 제목을 기준으로 오름차순 정렬해주세요.
```   
```
# SELECT
# TITLE,
# BOARD_ID,
# REPLY_ID,
# WRITER_ID,
# CONTENTS,
# CREATED_DATE
# FROM USED_GOODS_BOARD b
# JOIN USED_GOODS_REPLY r on b.BOARD_ID=r.BOARD_ID
# WHERE CREATED_DATE="2022-10"
# order by CREATED_DATE,TITLE
```

SELECT    
    b.TITLE,   
    b.BOARD_ID,    
    r.REPLY_ID,   
    r.WRITER_ID,   
    r.CONTENTS,   
    DATE_FORMAT(r.CREATED_DATE, '%Y-%m-%d') AS CREATED_DATE   
FROM USED_GOODS_BOARD b   
JOIN USED_GOODS_REPLY r    
    ON b.BOARD_ID = r.BOARD_ID   
WHERE DATE_FORMAT(b.CREATED_DATE, '%Y-%m') = '2022-10'   
ORDER BY r.CREATED_DATE , b.TITLE      
   
**#내가보낸문제**   
```
 2017년 1월 한 달 동안 택배사에 전달되었지만 배송 완료는 되지 않은 주문 건수를 택배사 도착일을 기준으로 집계하는 쿼리를 작성해주세요.
 쿼리 결과는 택배사 도착일을 기준으로 오름차순 정렬되어야 하고, 아래 컬럼을 포함해야 합니다.

delivered_carrier_date - 택배사 도착 날짜 (예: 2017-01-16)
orders - 택배사에 도착했지만, 고객에게 배송되지 않은 주문 건 수
 ```   
 
SELECT    
    DATE(order_delivered_carrier_date) AS delivered_carrier_date,   
    COUNT(*) AS orders   
FROM olist_orders_dataset   
WHERE order_delivered_carrier_date    BETWEEN '2017-01-01' AND '2017-01-31'   
    AND order_delivered_customer_date IS NULL      
    #고객에게 도착하지 않은 주문만 선택   
GROUP BY DATE(order_delivered_carrier_date)   
ORDER BY delivered_carrier_date
