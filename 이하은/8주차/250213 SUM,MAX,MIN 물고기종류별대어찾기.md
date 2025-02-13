# 문제 링크: https://school.programmers.co.kr/learn/courses/30/lessons/293261
# 풀이
이 문제는 가장 큰 물고기의 ID, 이름, 길이를 출력하면 되는 문제다. 레벨이 3단계인데도 불구하고 2레벨인 대장균 문제보다 쉬웠다. 가장 큰 물고기의 길이를 구해야되기 때문에 쿼리로 FISH_INFO 테이블에서 FISH_TYPE을 그룹화시켜 HAVING LENGTH = MAX(LENGTH)를 써줘 물고기 종류별로 큰 길이를 가진 물고기를 찾아준다. 그리고 WHERE문에서 FISH_INFO(fish) 테이블에서 FISH_TYPE을 추려내면 된다. 그 다음 SELECT문에서 fish.LENGTH로 길이를 출력시켜주면 된다.

```sql
SELECT ID, FISH_NAME, fish.LENGTH AS LENGTH
FROM FISH_INFO fish
JOIN FISH_NAME_INFO name
ON fish.FISH_TYPE = name.FISH_TYPE
WHERE fish.FISH_TYPE 
IN (
      SELECT FISH_TYPE
      FROM FISH_INFO
      GROUP BY FISH_TYPE
      HAVING LENGTH = MAX(LENGTH)
)
ORDER BY ID
```