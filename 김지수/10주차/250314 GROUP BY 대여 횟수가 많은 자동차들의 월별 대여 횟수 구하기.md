### 문제 링크
[대여 횟수가 많은 자동차들의 월별 대여 횟수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/151139)

### 풀이 방법
- 2022년 8월부터 10월까지의 대여 횟수가 5회 이상인 자동차 ID를 조회하는 공통 테이블을 작성한다.
- 2022년 8월부터 10월까지의 레코드 중에서 공통 테이블에 포함된 자동차 ID를 갖는 레코드만 남긴다.
- 월과 자동차 ID에 대해 그룹화한다.

### 소스 코드
```sql
WITH CAR_RENTAL_WITH_5_OR_MORE AS (
    SELECT CAR_ID
    FROM CAR_RENTAL_COMPANY_RENTAL_HISTORY
    WHERE YEAR(START_DATE) = 2022
    AND MONTH(START_DATE) BETWEEN 8 AND 10
    GROUP BY CAR_ID
    HAVING COUNT(CAR_ID) >= 5
)

SELECT MONTH(START_DATE) AS MONTH, CAR_ID, COUNT(*) AS RECORDS
FROM CAR_RENTAL_COMPANY_RENTAL_HISTORY 
WHERE YEAR(START_DATE) = 2022
AND MONTH(START_DATE) BETWEEN 8 AND 10
AND CAR_ID IN (SELECT CAR_ID 
               FROM CAR_RENTAL_WITH_5_OR_MORE)
GROUP BY MONTH(START_DATE), CAR_ID
HAVING COUNT(*) > 0
ORDER BY MONTH, CAR_ID DESC
```