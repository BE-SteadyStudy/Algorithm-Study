# 문제 링크: https://school.programmers.co.kr/learn/courses/30/lessons/131115
# 풀이
이 문제는 제일 비싼 식품을 하나 출력하는 문제다. 이전문제들 처럼 ORDER BY문으로 가격을 DESC로 정렬시켜 LIMIT 1로 제일 비싼 식품만 출력시키면 된다.

```sql
SELECT *
FROM FOOD_PRODUCT
ORDER BY PRICE DESC
LIMIT 1
```