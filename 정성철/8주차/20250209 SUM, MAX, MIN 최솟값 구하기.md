# 문제 링크 : https://school.programmers.co.kr/learn/courses/30/lessons/59038

## 문제 풀이 
MIN을 이용하면 가장 먼저 들어온 시간을 조회할 수 있습니다.

## 코드
```sql
-- MYSQL로 풀었습니다.
SELECT MIN(DATETIME) AS `시간` FROM ANIMAL_INS
```