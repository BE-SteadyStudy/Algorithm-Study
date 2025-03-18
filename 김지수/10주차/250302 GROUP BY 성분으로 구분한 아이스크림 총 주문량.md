### 문제 링크
[성분으로 구분한 아이스크림 총 주문량](https://school.programmers.co.kr/learn/courses/30/lessons/133026)

### 풀이 방법
- `FIRST_HALF` 테이블과 `ICECREAM_INFO` 테이블을 `FLAVOR` 칼럼에 대해 조인한다.
- 조인한 결과를 `INGREDIENT_TYPE` 칼럼에 대해 그룹화한다.
- `INGREDIENT_TYPE` 칼럼과 `SUM(TOTAL_ORDER)` 칼럼을 조회한다.
- `SUM(TOTAL_ORDER)`에 대해 오름차순 정렬한다.

### 소스 코드
```sql
SELECT INGREDIENT_TYPE, SUM(TOTAL_ORDER) AS TOTAL_ORDER
FROM FIRST_HALF, ICECREAM_INFO
WHERE FIRST_HALF.FLAVOR = ICECREAM_INFO.FLAVOR
GROUP BY INGREDIENT_TYPE
ORDER BY SUM(TOTAL_ORDER)
```