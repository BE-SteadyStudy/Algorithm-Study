# 문제 링크
https://school.programmers.co.kr/learn/courses/30/lessons/276013

# 풀이
DEVELOPER_INFOS 테이블에서 Python 스킬을 가진 개발자의 정보를 조회합니다.  
SKILL_1, 2, 3 중 적어도 하나가 Python인 개발자의 정보를 출력하면 됩니다.  
결과는 ID를 기준으로 오름차순 정렬합니다.

```sql
SELECT ID, EMAIL, FIRST_NAME, LAST_NAME
FROM DEVELOPER_INFOS
WHERE SKILL_1 = 'Python' OR SKILL_2 = 'Python' OR SKILL_3 = 'Python'
ORDER BY ID
```