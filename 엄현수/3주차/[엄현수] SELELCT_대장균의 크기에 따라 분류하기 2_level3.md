> https://school.programmers.co.kr/learn/courses/30/lessons/301649
>
> WITH 절과 PERCENT_RANK() 함수를 사용하여 퍼센티얼하고 CASE 구문 사용하여 크기를 나누었다.
```sql
WITH RANKED_DATA AS (
    SELECT
        ID, 
        PERCENT_RANK() OVER (ORDER BY SIZE_OF_COLONY) AS PER_RANK
    FROM ECOLI_DATA
)

SELECT ID,
    CASE
        WHEN PER_RANK <= 0.25 THEN 'LOW'
        WHEN PER_RANK <= 0.50 THEN 'MEDIUM'
        WHEN PER_RANK <= 0.75 THEN 'HIGH'
        ELSE 'CRITICAL'
    END AS COLONY_NAME
FROM RANKED_DATA
ORDER BY 1
```
