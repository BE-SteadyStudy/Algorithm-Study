# 문제 링크 : https://school.programmers.co.kr/learn/courses/30/lessons/273709

## 문제 풀이 
희귀도가 LEGEND인 아이템들을 선택해야 되므로 RARITY = 'LEGEND', 가격의 총 합이므로 SUM(PRICE) 를 하면 풀 수 있습니다.

## 코드
```sql
-- MYSQL로 풀었습니다.
SELECT SUM(PRICE) AS TOTAL_PRICE FROM ITEM_INFO
WHERE RARITY = 'LEGEND'
```