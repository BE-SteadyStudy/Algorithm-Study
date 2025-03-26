### 🔗 동명 동물 수 찾기
https://school.programmers.co.kr/learn/courses/30/lessons/59041

### ❓ 풀이 방법
WHERE 절로 이름이 없는 동물을 집계에서 제외했다.

### 💡소스 코드
````sql
SELECT NAME, COUNT(ANIMAL_ID) AS COUNT
FROM ANIMAL_INS
WHERE NAME IS NOT NULL
GROUP BY NAME
HAVING COUNT(ANIMAL_ID)>1
ORDER BY NAME;
````