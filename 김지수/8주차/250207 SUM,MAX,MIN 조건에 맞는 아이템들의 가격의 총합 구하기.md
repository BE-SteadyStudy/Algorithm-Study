### 문제 링크
[조건에 맞는 아이템들의 가격의 총합 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/273709)

### 풀이 방법
- ITEM_INFO 테이블에서 PARITY 칼럼의 값이 'LEGEND'인 레코드를 필터링한다.
- 필터링된 레코드의 PRICE 총합을 조회한다.
- 별칭을 TOTAL_PRICE로 지정한다.

### 소스 코드
```sql
SELECT SUM(PRICE) AS TOTAL_PRICE
FROM ITEM_INFO 
WHERE RARITY = 'LEGEND'
```