### 🔗 가장 비싼 상품 구하기
https://school.programmers.co.kr/learn/courses/30/lessons/131697

### ❓ 풀이 방법
MAX()로 가장 높은 판매가를 조회했다.

### 💡소스 코드
````sql
SELECT MAX(PRICE) AS MAX_PRICE
FROM PRODUCT;
````