### 문제 링크
[가격이 제일 비싼 식품의 정보 출력하기](https://school.programmers.co.kr/learn/courses/30/lessons/131115)

### 풀이 방법
- 서브 쿼리에서 FOOD_PRODUCT.PRICE의 최댓값을 PRICE라는 별칭으로 지정해 반환한다.
- 공통 테이블의 이름을 MAX_RESULT로 지정한 뒤 서브 쿼리의 반환 결과를 참조하게 한다.
- FOOD_PRODUCT 테이블에서 PRICE 칼럼의 값이 MAX_RESULT.PRICE와 동일한 레코드를 필터링한다.
- FOOD_PRODUCT의 모든 칼럼을 조회한다.

### 소스 코드
```sql
WITH MAX_RESULT AS (
    SELECT MAX(PRICE) AS PRICE
    FROM FOOD_PRODUCT
)

SELECT FOOD_PRODUCT.*
FROM FOOD_PRODUCT, MAX_RESULT
WHERE FOOD_PRODUCT.PRICE = MAX_RESULT.PRICE
```