### 🔗 물고기 종류 별 대어 찾기
https://school.programmers.co.kr/learn/courses/30/lessons/293261

### ❓ 풀이 방법
RANK()로 FISH_TYPE 별 물고기 크기 순위를 구하고,
종류 별 가장 큰 물고기를 골랐다.

### 💡소스 코드
````sql
WITH RankedFish AS (
    SELECT
        FI.ID,
        FN.FISH_NAME,
        FI.LENGTH,
        RANK() OVER (PARTITION BY FI.FISH_TYPE ORDER BY FI.LENGTH DESC) AS rnk
    FROM FISH_INFO FI
    LEFT JOIN FISH_NAME_INFO FN
    ON FI.FISH_TYPE=FN.FISH_TYPE
)
SELECT ID, FISH_NAME, LENGTH
FROM RankedFish
WHERE rnk=1
ORDER BY ID;
````