> https://school.programmers.co.kr/learn/courses/30/lessons/131536

```sql
SELECT USER_ID, PRODUCT_ID
FROM ONLINE_SALE
GROUP BY USER_ID, PRODUCT_ID
HAVING COUNT(*) > 1
ORDER BY 1, 2 DESC
```
