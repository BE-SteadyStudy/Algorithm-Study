# 문제 링크: https://school.programmers.co.kr/learn/courses/30/lessons/59415
# 풀이
이 문제는 가장 최근에 들어온 동물이 언제 들어왔는지 조회해서 출력하면 된다. DATETIME 컬럼을 ORDER BY DESC로 불러와 출력하면 된다. 이 때 한마리만 출력하면 되므로, LIMIT 1을 써준다.

```sql
SELECT DATETIME AS '시간'
FROM ANIMAL_INS
ORDER BY DATETIME DESC
LIMIT 1
```