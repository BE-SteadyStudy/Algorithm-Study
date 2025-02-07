# 문제 링크: https://school.programmers.co.kr/learn/courses/30/lessons/59038
# 풀이
이 문제는 이전에 푼 최댓값 구하기와 비슷한 문제다. DESC가 아닌 ASC나 비워두면, 알아서 오름차순 정렬을 해준다.

```sql
SELECT DATETIME "시간"
FROM ANIMAL_INS
ORDER BY DATETIME
LIMIT 1
```