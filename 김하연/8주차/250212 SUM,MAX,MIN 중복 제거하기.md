### 🔗 중복 제거하기
https://school.programmers.co.kr/learn/courses/30/lessons/59408

### ❓ 풀이 방법
WHERE 절과 DISTINCT로 조건에 맞는 이름의 수를 구했다.

### 💡소스 코드
````sql
SELECT COUNT(DISTINCT NAME)
FROM ANIMAL_INS
WHERE NAME IS NOT NULL;
````