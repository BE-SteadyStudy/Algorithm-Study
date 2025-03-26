### 🔗 성분으로 구분한 아이스크림 총 주문량
https://school.programmers.co.kr/learn/courses/30/lessons/133026

### ❓ 풀이 방법
SUM 함수로 총 주문량을 계산했다.

### 💡소스 코드
````sql
SELECT II.INGREDIENT_TYPE, SUM(FH.TOTAL_ORDER) AS TOTAL_ORDER
FROM FIRST_HALF FH
JOIN ICECREAM_INFO II ON FH.FLAVOR=II.FLAVOR
GROUP BY II.INGREDIENT_TYPE
ORDER BY TOTAL_ORDER;
````