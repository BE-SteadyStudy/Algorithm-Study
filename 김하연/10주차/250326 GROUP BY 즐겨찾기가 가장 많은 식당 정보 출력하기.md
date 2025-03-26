### 🔗 즐겨찾기가 가장 많은 식당 정보 출력하기
https://school.programmers.co.kr/learn/courses/30/lessons/131123

### ❓ 풀이 방법
GROUP BY가 MAX 함수를 제대로 처리하지 못한다는 것을 알게 되어 서브 쿼리로 분리했다.

### 💡소스 코드
````sql
SELECT FOOD_TYPE, REST_ID, REST_NAME, FAVORITES
FROM REST_INFO
WHERE FAVORITES IN (
    SELECT MAX(FAVORITES)
    FROM REST_INFO
    GROUP BY FOOD_TYPE
)
GROUP BY FOOD_TYPE
ORDER BY FOOD_TYPE DESC;
````