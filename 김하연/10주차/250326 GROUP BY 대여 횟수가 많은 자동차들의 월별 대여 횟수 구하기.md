### 🔗 대여 횟수가 많은 자동차들의 월별 대여 횟수 구하기
https://school.programmers.co.kr/learn/courses/30/lessons/151139

### ❓ 풀이 방법
처음엔 서브 쿼리에만 날짜 조건문을 붙였는데, 메인 쿼리에도 붙여야 날짜 조건에 맞는 데이터만 조회된다.

### 💡소스 코드
````sql
SELECT MONTH(START_DATE) AS MONTH, CAR_ID, COUNT(CAR_ID) AS RECORDS
FROM CAR_RENTAL_COMPANY_RENTAL_HISTORY
WHERE CAR_ID IN (
    SELECT CAR_ID
    FROM CAR_RENTAL_COMPANY_RENTAL_HISTORY
    WHERE START_DATE BETWEEN '2022-08-01' AND '2022-11-01'
    GROUP BY CAR_ID
    HAVING COUNT(CAR_ID)>4
) AND START_DATE BETWEEN '2022-08-01' AND '2022-11-01'
GROUP BY MONTH, CAR_ID
HAVING RECORDS>0
ORDER BY MONTH, CAR_ID DESC;
````