### 문제 링크
[자동차 종류별 특정 옵션이 포함된 자동차 수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/151137)

### 풀이 방법
- `CAR_RENTAL_COMPANY_CAR` 테이블에서 `통풍시트`, `열선시트`, `가죽시트` 중 하나 이상의 옵션이 포함된 레코드를 필터링한다.
- `CAR_TYPE` 칼럼에 대해 그룹화한다.
- `CAR_TYPE` 칼럼과 `COUNT(CAR_TYPE)` 칼럼을 조회한다.
- `CAR_TYPE` 칼럼에 대해 오름차순 정렬한다.

### 소스 코드
```sql
SELECT CAR_TYPE, COUNT(CAR_TYPE) AS CARS
FROM CAR_RENTAL_COMPANY_CAR 
WHERE OPTIONS LIKE '%통풍시트%'
OR OPTIONS LIKE '%열선시트%'
OR OPTIONS LIKE '%가죽시트%'
GROUP BY CAR_TYPE
ORDER BY CAR_TYPE
```