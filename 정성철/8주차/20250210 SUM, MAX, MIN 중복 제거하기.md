# 문제 링크 : https://school.programmers.co.kr/learn/courses/30/lessons/59408

## 문제 풀이 
DISTINCT를 사용하면 중복된 값을 제거할 수 있습니다. 이름이 NULL인 경우를 제외해야 하고(IS NOT NULL 사용), 갯수를 구해야 하므로 COUNT를 사용합니다.

## 코드
```sql
-- MYSQL로 풀었습니다.
SELECT COUNT(DISTINCT NAME) AS COUNT FROM ANIMAL_INS
WHERE NAME IS NOT NULL
```