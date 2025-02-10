# 문제 링크
https://school.programmers.co.kr/learn/courses/30/lessons/59415

# 풀이
MAX 함수를 이용하여 DATETIME의 최댓값을 구하면 가장 최근 날짜입니다.

```sql
SELECT MAX(DATETIME) 시간
FROM ANIMAL_INS
```