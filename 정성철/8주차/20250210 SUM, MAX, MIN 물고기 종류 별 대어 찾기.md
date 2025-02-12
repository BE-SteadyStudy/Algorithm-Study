# 문제 링크 : https://school.programmers.co.kr/learn/courses/30/lessons/293261

## 문제 풀이 
우선, FISH_INFO의 서브쿼리를 이용해서 FISH_TYPE에 해당하는 최대 길이를 조회하게 합니다.<br/>
NAME은 FISH_NAME_INFO 에 있고, FISH_TYPE으로 묶이므로 FISH_TYPE을 이용해 JOIN합니다.<br/>
마지막으로 ID를 기준으로 오름차순 하면 됩니다.


## 코드
```sql
-- MYSQL로 풀었습니다.
SELECT INFO.ID, NAME.FISH_NAME, INFO.LENGTH AS LENGTH FROM FISH_INFO INFO
INNER JOIN FISH_NAME_INFO NAME ON INFO.FISH_TYPE = NAME.FISH_TYPE
WHERE INFO.LENGTH = (SELECT MAX(LENGTH) FROM FISH_INFO WHERE FISH_TYPE = INFO.FISH_TYPE)
ORDER BY INFO.ID
```