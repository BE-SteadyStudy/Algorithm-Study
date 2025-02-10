# 문제 링크
https://school.programmers.co.kr/learn/courses/30/lessons/131115

# 풀이
FOOD_PRODUCT 테이블의 데이터를 가격을 기준으로 내림차순으로 정렬합니다.  
LIMIT를 이용하여 가장 상위 데이터를 출력합니다.

```sql
SELECT *
FROM FOOD_PRODUCT
ORDER BY PRICE DESC
LIMIT 1
```