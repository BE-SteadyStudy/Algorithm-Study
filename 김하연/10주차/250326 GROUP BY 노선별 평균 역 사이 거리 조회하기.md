### 🔗 노선별 평균 역 사이 거리 조회하기
https://school.programmers.co.kr/learn/courses/30/lessons/284531

### ❓ 풀이 방법
CONCAT 함수로 단위를 붙였고 ROUND 함수로 소수점 자릿수를 정했다.

### 💡소스 코드
````sql
SELECT ROUTE, CONCAT(ROUND(SUM(D_BETWEEN_DIST), 1), 'km') AS TOTAL_DISTANCE, CONCAT(ROUND(AVG(D_BETWEEN_DIST), 2), 'km') AS AVERAGE_DISTANCE
FROM SUBWAY_DISTANCE
GROUP BY ROUTE
ORDER BY ROUND(SUM(D_BETWEEN_DIST), 1) DESC;
````