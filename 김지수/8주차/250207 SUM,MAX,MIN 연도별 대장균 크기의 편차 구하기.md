### 문제 링크
[연도별 대장균 크기의 편차 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/299310)

### 풀이 방법
- 공통 테이블(MAX_RESULT)을 이용해 각 연도별 SIZE_OF_COLONY의 최댓값을 계산한다.
- ECOLI_DATA 테이블과 MAX_RESULT 테이블을 분화된 연도를 기준으로 JOIN한다. 
- 각 레코드에서 연도별 최댓값과 실제 SIZE_OF_COLONY의 차이를 계산한다.
- 연도(YEAR), 차이(YEAR_DEV)에 대해 오름차순 정렬한다.

### 소스 코드
```sql
WITH MAX_RESULT AS (
    SELECT 
        YEAR(DIFFERENTIATION_DATE) AS YEAR, 
        MAX(SIZE_OF_COLONY) AS MAX_SIZE
    FROM
        ECOLI_DATA
    GROUP BY 
        YEAR(DIFFERENTIATION_DATE)
)

SELECT 
    YEAR(DIFFERENTIATION_DATE) AS YEAR,
    (MAX_RESULT.MAX_SIZE - ECOLI_DATA.SIZE_OF_COLONY) AS YEAR_DEV, 
    ID
FROM 
    ECOLI_DATA
JOIN 
    MAX_RESULT
ON 
    YEAR(ECOLI_DATA.DIFFERENTIATION_DATE) = MAX_RESULT.YEAR
ORDER BY
    YEAR, 
    YEAR_DEV
```