### 🔗 최솟값 구하기
https://school.programmers.co.kr/learn/courses/30/lessons/59038

### ❓ 풀이 방법
MIN()로 가장 예전 날짜를 조회했다.

### 💡소스 코드
````sql
SELECT MIN(DATETIME) AS '시간'
FROM ANIMAL_INS;
````