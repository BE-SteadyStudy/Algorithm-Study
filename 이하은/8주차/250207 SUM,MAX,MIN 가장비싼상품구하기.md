# 문제 링크: https://school.programmers.co.kr/learn/courses/30/lessons/131697
# 풀이
이 문제는 간단하게 한 테이블에서 판매 중인 상품 중 가장 높은 판매가를 출력하면 된다. ORDER BY로 PRICE를 내림차순 하여 제일 위에 있는 것을 LIMIT 1로 하나만 출력시켜주면 된다.

```sql
SELECT PRICE MAX_PRICE FROM PRODUCT 
ORDER BY PRICE DESC
LIMIT 1;
```