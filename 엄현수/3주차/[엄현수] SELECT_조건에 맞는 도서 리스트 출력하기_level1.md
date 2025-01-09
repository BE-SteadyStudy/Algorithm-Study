> https://school.programmers.co.kr/learn/courses/30/lessons/144853
>
> 연도를 구하는 것에 YEAR() = 2021을 사용
```sql
SELECT BOOK_ID, DATE_FORMAT(PUBLISHED_DATE, '%Y-%m-%d') AS PUBLISHED_DATE
FROM BOOK
WHERE YEAR(PUBLISHED_DATE) = 2021 AND CATEGORY = '인문'
ORDER BY PUBLISHED_DATE;
```
