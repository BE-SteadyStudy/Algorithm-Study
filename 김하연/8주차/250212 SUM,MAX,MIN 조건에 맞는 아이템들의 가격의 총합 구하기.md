### 🔗 조건에 맞는 아이템들의 가격의 총합 구하기
https://school.programmers.co.kr/learn/courses/30/lessons/273709

### ❓ 풀이 방법
WHERE 절로 조건에 맞는 행을 고르고 SUM()으로 가격의 합을 구했다.

### 💡소스 코드
````sql
SELECT SUM(PRICE) AS TOTAL_PRICE
FROM ITEM_INFO
WHERE RARITY='LEGEND';
````