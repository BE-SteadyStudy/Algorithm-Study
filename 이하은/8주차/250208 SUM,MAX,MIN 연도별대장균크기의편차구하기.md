# 문제 링크: https://school.programmers.co.kr/learn/courses/30/lessons/299310
# 풀이
이 문제는 대장균의 분화된 연도와 크기에 대한 편차를 구해 출력하는 문제다. ID를 제외하고 분화된 연도(YEAR), 분화된 연도별 대장균 크기의 편차(YEAR_DEV)를 따로 구해 출력시켜줘야 한다. 우선 분화된 연도부터 구했다. 이중쿼리로 따로 first라는 이름을 붙여 DIFFERENTIATION_DATE의 연도를 포함해 개체의 크기(SIZE_OF_COLONY)와 ID를 뽑아냈다. 사실 편차만 아니었으면 이중쿼리를 쓸 필요가 없었다. 편차를 구하기 위해 JOIN ON을 사용해 두번째 쿼리를 작성해준다. 첫번째 쿼리랑 똑같이 만들어 주되, MAX(SIZE_OF_COLONY)를 써 큰 개체를 골라내주게 한다. 그리고 년도별로 그룹화를 시키기 위해 GROUPB BY를 사용해주고 second라는 이름을 붙여줬다. 이제 SELECT에서 (second.MAX - first.SIZE_OF_COLONY)을 써 두번째 쿼리에 있는 가장 큰 개체 크기에서 첫번째 쿼리에 있는 개체 크기를 빼줘 편차를 구해 출력해주면 된다.

```sql
SELECT first.YEAR AS YEAR, (second.MAX - first.SIZE_OF_COLONY) AS YEAR_DEV, first.ID
FROM (
    SELECT YEAR(DIFFERENTIATION_DATE) AS YEAR, SIZE_OF_COLONY, ID
    FROM ECOLI_DATA) AS first
JOIN (
    SELECT YEAR(DIFFERENTIATION_DATE) AS YEAR, MAX(SIZE_OF_COLONY) AS MAX
    FROM ECOLI_DATA
    GROUP BY YEAR(DIFFERENTIATION_DATE)) AS second
ON first.YEAR = second.YEAR
ORDER BY YEAR, YEAR_DEV;
```