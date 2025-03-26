### 🔗 조건에 맞는 사원 정보 조회하기
https://school.programmers.co.kr/learn/courses/30/lessons/284527

### ❓ 풀이 방법
LIMIT으로 평가 점수가 가장 높은 데이터 한 행만 출력했다.

### 💡소스 코드
````sql
SELECT SUM(G.SCORE) AS SCORE, G.EMP_NO, E.EMP_NAME, E.POSITION, E.EMAIL
FROM HR_GRADE G
JOIN HR_EMPLOYEES E ON E.EMP_NO=G.EMP_NO
WHERE G.YEAR=2022
GROUP BY G.EMP_NO
ORDER BY SCORE DESC LIMIT 1;
````