# 문제 링크
https://school.programmers.co.kr/learn/courses/30/lessons/298515

# 풀이
MAX 함수를 이용해서 물고기 길이의 최댓값을 구하고 CONCAT 함수를 이용하여 cm를 붙여서 출력합니다.

```sql
SELECT CONCAT(MAX(LENGTH), 'cm') MAX_LENGTH
FROM FISH_INFO
```