# 문제 링크
https://school.programmers.co.kr/learn/courses/30/lessons/59038

# 풀이
MIN 함수를 이용하여 DATETIME의 최솟값을 구하면 가장 예전 날짜입니다.

```sql
SELECT MIN(DATETIME) 시간
FROM ANIMAL_INS
```