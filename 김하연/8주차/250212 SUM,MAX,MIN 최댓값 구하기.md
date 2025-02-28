### 🔗 최댓값 구하기
https://school.programmers.co.kr/learn/courses/30/lessons/59415

### ❓ 풀이 방법
MAX()로 가장 최근 날짜를 조회했다.

### 💡소스 코드
````sql
SELECT MAX(DATETIME) AS '시간'
FROM ANIMAL_INS;
````