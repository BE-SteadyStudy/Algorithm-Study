# 문제 링크: https://school.programmers.co.kr/learn/courses/30/lessons/59408
# 풀이
이 문제는 동물의 이름을 세어주면 된다. COUNT를 써 NAME을 세어주고 앞에 DISTINCT를 써 중복을 제외시켜주면 된다.

```sql
SELECT COUNT(DISTINCT NAME)
FROM ANIMAL_INS
```