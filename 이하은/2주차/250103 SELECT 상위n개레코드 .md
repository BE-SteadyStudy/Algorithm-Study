# 문제 링크: https://school.programmers.co.kr/learn/courses/30/lessons/59405
# 풀이
이 문제는 동물 보호소에 가장 먼저 들어온 동물의 이름만을 조회하면 된다. 매우 간단히 SELECT에서 NAME만 써 이름만 나오게 하고, 가장 먼저 들어온 동물을 오름차순으로 정렬해야되므로 ORDER BY에 DATETIME을 써주면 된다. 역시 오름차순이 기본이라 ASC를 생략해도 된다. 나오는 동물은 한마리므로 LIMIT 1을 써 줘 한마리만 출력하게 만들면 된다.

```sql
SELECT NAME FROM ANIMAL_INS
ORDER BY DATETIME
    LIMIT 1
```