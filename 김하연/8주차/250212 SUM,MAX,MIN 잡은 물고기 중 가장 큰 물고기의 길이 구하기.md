### 🔗 잡은 물고기 중 가장 큰 물고기의 길이 구하기
https://school.programmers.co.kr/learn/courses/30/lessons/298515

### ❓ 풀이 방법
FORMAT()으로 ##.##에 맞게 포맷팅했고 CONCAT()으로 cm를 붙여 출력했다.

### 💡소스 코드
````sql
SELECT CONCAT(FORMAT(MAX(LENGTH), 2), 'cm') AS MAX_LENGTH
FROM FISH_INFO;
````