# 문제 링크
https://school.programmers.co.kr/learn/courses/30/lessons/59405

# 풀이
ANIMAL_INS 테이블에서 동물의 이름을 조회합니다.  
가장 먼저 들어온 동물의 이름을 얻기 위해서 보호 시작일을 기준으로 오름차순 정렬하고 LIMIT를 이용하여 상위 1개 데이터만 가져옵니다.

```sql
SELECT NAME
FROM ANIMAL_INS
ORDER BY DATETIME
LIMIT 1
```