> https://school.programmers.co.kr/learn/courses/30/lessons/276034

```sql
SELECT DISTINCT ID, EMAIL, FIRST_NAME, LAST_NAME
FROM DEVELOPERS JOIN SKILLCODES ON SKILL_CODE & CODE
WHERE NAME IN ('Python' , 'C#')
ORDER BY 1;
```
