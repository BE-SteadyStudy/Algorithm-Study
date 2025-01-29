# 문제 링크 : https://school.programmers.co.kr/learn/courses/30/lessons/276013

## 문제 풀이 
Python의 SKILL을 가진 사람을 찾으므로, SKILL 1 ~ 3이 컬럼에 해당하니 해당 값이 python인 값을 or로 찾으면 됩니다.<br/>
ID값으로 오름차순을 해달라고 했으므로 ORDER BY ID

## 코드
```sql
-- MYSQL로 풀었습니다.
SELECT ID, EMAIL, FIRST_NAME, LAST_NAME FROM DEVELOPER_INFOS
WHERE SKILL_1 = 'Python' OR SKILL_2 = 'Python' OR SKILL_3 = 'Python'
ORDER BY ID
```