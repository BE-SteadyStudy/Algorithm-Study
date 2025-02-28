# 문제 링크
https://school.programmers.co.kr/learn/courses/30/lessons/273709

# 풀이
ITEM_INFO 테이블에서 RARITY가 LEGEND인 데이터의 가격의 총합을 SUM 함수를 이용해서 구합니다.  

```sql
SELECT SUM(PRICE) TOTAL_PRICE
FROM ITEM_INFO
WHERE RARITY = 'LEGEND'
```