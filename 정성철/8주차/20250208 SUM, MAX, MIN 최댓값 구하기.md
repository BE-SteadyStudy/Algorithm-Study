# 문제 링크 : https://school.programmers.co.kr/learn/courses/30/lessons/59415

## 문제 풀이 
MAX를 이용하면 가장 늦게 들어온 시간을 조회할 수 있습니다.

## 코드
```sql
-- MYSQL로 풀었습니다.
SELECT MAX(DATETIME) as `시간` FROM ANIMAL_INS
```