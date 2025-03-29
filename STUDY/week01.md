#승화님문제   
##부모의 형질을 모두 보유한 대장균의 ID(ID), 대장균의 형질(GENOTYPE), 부모 대장균의 형질(PARENT_GENOTYPE)을 출력하는 SQL 문을 작성해주세요. 이때 결과는 ID에 대해 오름차순 정렬해주세요.

SELECT   
ID,   
GENOTYPE,   
PARENT_GENOTYPE
FROM ECOLI_DATA
WHERE ID="2"or"3"or"7"or"8"
#부모의 형질을 모두 보유한 ID: 2,3,7,8
ORDER BY ID
