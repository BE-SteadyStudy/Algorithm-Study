### 문제 링크
[가장 비싼 상품 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/131697)

### 풀이 방법
- PRODUCT 테이블에서 PRICE 칼럼의 최댓값을 조회한다.
- 별칭을 MAX_PRICE로 지정한다.

### 소스 코드
```sql
SELECT MAX(PRICE) AS MAX_PRICE
FROM PRODUCT 
```