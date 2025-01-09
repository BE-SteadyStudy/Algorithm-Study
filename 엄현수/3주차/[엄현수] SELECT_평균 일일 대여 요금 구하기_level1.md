> https://school.programmers.co.kr/learn/courses/30/lessons/151136
>
> 평균값을 소수점 반올림하려면 ROUND()를 사용하면 됨.

```sql
SELECT ROUND(AVG(DAILY_FEE)) as AVERAGE_FEE
FROM CAR_RENTAL_COMPANY_CAR
WHERE CAR_TYPE LIKE "SUV"
```
