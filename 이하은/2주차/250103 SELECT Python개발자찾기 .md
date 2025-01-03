# 문제 링크: https://school.programmers.co.kr/learn/courses/30/lessons/276013
# 풀이
Python 스킬을 가진 개발자의 정보를 조회하는 문제다. 이 문제는 독특하게도 보유하고 있는 스킬을 적어둔 컬럼인 SKILL 컬럼이 3가지다. 그러므로 3가지를 조회해야된다. 간단히 WHERE문으로 SKILL 컬럼 3가지에서 'Python'이 있는지 조회하면 된다. 이때 AND가 아닌 OR로 해야 각각의 SKILL 컬럼에 Python이 한개라도 있으면 출력되도록 조회한다.

```sql
SELECT ID, EMAIL, FIRST_NAME, LAST_NAME
FROM DEVELOPER_INFOS
WHERE SKILL_1 = 'Python' OR SKILL_2 = 'Python' OR SKILL_3 = 'Python'
ORDER BY ID
```