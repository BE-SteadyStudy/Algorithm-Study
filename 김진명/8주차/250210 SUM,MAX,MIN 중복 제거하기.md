# 문제 링크
https://school.programmers.co.kr/learn/courses/30/lessons/59408

# 풀이
COUNT 함수를 사용하서 이름의 수를 구하되 DISTINCT를 이용해서 중복된 이름을 제거합니다.

```sql
SELECT COUNT(DISTINCT NAME)
FROM ANIMAL_INS
```