### 🔗 진료과별 총 예약 횟수 출력하기
https://school.programmers.co.kr/learn/courses/30/lessons/132202

### ❓ 풀이 방법
COUNT 함수로 총 예약 횟수를 계산했다.

### 💡소스 코드
````sql
SELECT MCDP_CD AS '진료과코드', COUNT(*) AS '5월예약건수'
FROM APPOINTMENT
WHERE APNT_YMD LIKE '2022-05%'
GROUP BY MCDP_CD
ORDER BY COUNT(*), MCDP_CD;
````