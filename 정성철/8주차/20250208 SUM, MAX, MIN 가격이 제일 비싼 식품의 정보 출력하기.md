# 문제 링크 : https://school.programmers.co.kr/learn/courses/30/lessons/131115

## 문제 풀이 
Order by 로 PRICE를 내림차순 한 이후, LIMIT로 가장 위의 것만 조회하면 풀립니다.

## 코드
```sql
-- MYSQL로 풀었습니다.
SELECT PRODUCT_ID, PRODUCT_NAME, PRODUCT_CD, CATEGORY, PRICE FROM FOOD_PRODUCT
ORDER BY PRICE DESC
LIMIT 1
```