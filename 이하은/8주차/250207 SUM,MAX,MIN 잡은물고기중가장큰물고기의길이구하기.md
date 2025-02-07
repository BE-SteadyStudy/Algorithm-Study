# 문제 링크: https://school.programmers.co.kr/learn/courses/30/lessons/298515
# 풀이
FISH_INFO 테이블에서 가장 큰 물고기의 길이를 cm를 붙여 출력하면 되는 문제다. 이 때 컬럼명은 'MAX_LENGTH'로 지정해주면 된다. 간단히 CONCAT을 써 MAX()와 'cm'를 붙여준다. 그리고 AS MAX_LENGTH로 컬럼명을 지정해주면 된다. 

```sql
SELECT CONCAT(MAX(LENGTH), 'cm') AS MAX_LENGTH
FROM FISH_INFO
```