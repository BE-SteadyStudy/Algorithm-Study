## 문제 링크

Link : [Python 개발자 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/276013)

## 문제
DEVELOPER_INFOS 테이블에서 Python 스킬을 가진 개발자의 정보를 조회하려 합니다. </br>
Python 스킬을 가진 개발자의 ID, 이메일, 이름, 성을 조회하는 SQL 문을 작성해 주세요.</br>
결과는 ID를 기준으로 오름차순 정렬해 주세요.

## 문제 풀이

1. 각 SKILL 에 Python 이 포함되어 있는지 검사
2. 이후 ID로 정렬하여 결과 출력

## SQL 코드

```sql
SELECT
    ID,
    EMAIL,
    FIRST_NAME,
    LAST_NAME
FROM
    DEVELOPER_INFOS
WHERE
    SKILL_1 LIKE "Python"
    or
    SKILL_2 LIKE "Python"
    or
    SKILL_3 LIKE "Python"
ORDER BY
    ID;
```