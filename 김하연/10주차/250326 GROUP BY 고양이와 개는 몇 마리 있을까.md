### 🔗 고양이와 개는 몇 마리 있을까
https://school.programmers.co.kr/learn/courses/30/lessons/59040

### ❓ 풀이 방법
COUNT 함수로 종별 마릿수를 계산했다.

### 💡소스 코드
````sql
SELECT ANIMAL_TYPE, COUNT(ANIMAL_ID)
FROM ANIMAL_INS
GROUP BY ANIMAL_TYPE
ORDER BY ANIMAL_TYPE;
````