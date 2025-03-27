### 🔗 자동차 대여 기록에서 대여중 / 대여 가능 여부 구분하기
https://school.programmers.co.kr/learn/courses/30/lessons/157340

### ❓ 풀이 방법
대여중 / 대여 가능을 CASE문으로 구분했다.

### 💡소스 코드
````sql
SELECT CAR_ID,
       CASE
           WHEN CAR_ID IN (
               SELECT CAR_ID
               FROM CAR_RENTAL_COMPANY_RENTAL_HISTORY
               WHERE '2022-10-16' BETWEEN START_DATE AND END_DATE
           ) THEN '대여중'
           ELSE '대여 가능'
       END AVAILABILITY
FROM CAR_RENTAL_COMPANY_RENTAL_HISTORY
GROUP BY CAR_ID
ORDER BY CAR_ID DESC;
````