### 🔗 가격이 제일 비싼 식품의 정보 출력하기
https://school.programmers.co.kr/learn/courses/30/lessons/131115

### ❓ 풀이 방법
가장 높은 가격을 구하는 서브쿼리를 작성해서 해당하는 행을 골랐다.

### 💡소스 코드
````sql
SELECT *
FROM FOOD_PRODUCT
WHERE PRICE = (SELECT MAX(PRICE) FROM FOOD_PRODUCT)
````