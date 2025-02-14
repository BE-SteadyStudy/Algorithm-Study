### 🔗 Python 개발자 찾기
https://school.programmers.co.kr/learn/courses/30/lessons/276013

### ❓ 풀이 방법
`WHERE`절에 OR을 사용해 Python 스킬을 가진 개발자를 골랐다.

### 💡소스 코드
````sql
SELECT ID, EMAIL, FIRST_NAME, LAST_NAME
FROM DEVELOPER_INFOS
WHERE SKILL_1='Python' OR SKILL_2='Python' OR SKILL_3='Python'
ORDER BY ID;
````