# 문제 링크: https://school.programmers.co.kr/learn/courses/30/lessons/273709
# 풀이
이 문제는 희귀도가 LEGEND인 아이템의 가격을 더해주면 된다. SUM()으로 가격을 더해주고 컬럼명이 TOTAL_PRICE이므로 옆에 AS(제외가능) TOTAL_PRICE을 붙여준다. 그리고 WHERE 문으로 LEGEND인 아이템만 고르게 한다.

```sql
SELECT SUM(PRICE) TOTAL_PRICE
FROM ITEM_INFO
WHERE RARITY = 'LEGEND'
```