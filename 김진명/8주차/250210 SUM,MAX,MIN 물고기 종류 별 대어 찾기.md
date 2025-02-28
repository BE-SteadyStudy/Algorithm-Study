# 문제 링크
https://school.programmers.co.kr/learn/courses/30/lessons/293261

# 풀이
GROUP BY를 이용해서 물고기 종류와 길이의 최댓값을 구합니다.  
물고기 이름을 출력하기 위해 FISH_INFO와 FISN_NAME_INFO 테이블을 조인합니다.  
조인한 테이블에서 FISH_TYPE과 LENGTH가 서브 쿼리에 속하는 데이터만 출력합니다.  
데이터는 ID를 기준으로 오름차순으로 정렬합니다.

```sql
SELECT ID, FISH_NAME, LENGTH
FROM FISH_INFO I JOIN FISH_NAME_INFO N ON I.FISH_TYPE = N.FISH_TYPE
WHERE (I.FISH_TYPE, LENGTH) IN (
    SELECT FISH_TYPE, MAX(LENGTH)
    FROM FISH_INFO
    GROUP BY FISH_TYPE
)
ORDER BY ID
```