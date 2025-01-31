### 문제 링크
[파이썬 개발자 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/276013)

### 풀이 방법
- DEVELOPER_INFOS 테이블에서 SKILL_1 또는 SKILL_2 또는 SKILL_3이 'Python'인 레코드를 필터링한다.
- 필터링된 결과를 ID에 대해 오름차순 정렬한다.
- ID, EMAIL, FIRST_NAME, LAST_NAME 칼럼을 조회한다.

### 소스 코드
```sql
SELECT ID, EMAIL, FIRST_NAME, LAST_NAME
FROM DEVELOPER_INFOS
WHERE SKILL_1 = 'Python' OR SKILL_2 = 'Python' OR SKILL_3 = 'Python'
ORDER BY ID
```