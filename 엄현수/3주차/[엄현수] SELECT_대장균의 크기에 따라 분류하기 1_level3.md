> https://school.programmers.co.kr/learn/courses/30/lessons/299307
>
> case 구문사용 크기별로 결과를 나누었음
```sql
SELECT ID,
CASE
    WHEN SIZE_OF_COLONY > 1000 THEN 'HIGH'
    WHEN SIZE_OF_COLONY > 100 THEN 'MEDIUM'
    ELSE 'LOW'
END AS SIZE
FROM ECOLI_DATA
ORDER BY ID ;
```
