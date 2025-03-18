### 문제 링크
[가격대별 상품 개수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/131530)

### 풀이 방법
- `PRODUCT` 테이블에서 `(PRICE DIV 10000)`를 기준으로 그룹화한다.
    - 이때, `DIV`는 정수 나눗셈의 몫을 반환한다. 
- `(PRICE DIV 10000) * 10000` 값과 `COUNT(PRODUCT_ID)` 값을 조회한다.
- `(PRICE DIV 10000)`에 대해 오름차순 정렬한다.

### 소스 코드
```sql
SELECT (PRICE DIV 10000) * 10000 AS PRICE_GROUP, COUNT(PRODUCT_ID) AS PRODUCTS
FROM PRODUCT
GROUP BY (PRICE DIV 10000)
ORDER BY (PRICE DIV 10000)
```