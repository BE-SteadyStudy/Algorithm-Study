### 🔗 가격대 별 상품 개수 구하기
https://school.programmers.co.kr/learn/courses/30/lessons/131530

### ❓ 풀이 방법
DIV로 몫을 구해 가격대를 계산했다.

### 💡소스 코드
````sql
SELECT (PRICE DIV 10000 * 10000) AS PRICE_GROUP, COUNT(PRODUCT_ID) AS PRODUCTS
FROM PRODUCT
GROUP BY PRICE_GROUP
ORDER BY PRICE_GROUP;
````