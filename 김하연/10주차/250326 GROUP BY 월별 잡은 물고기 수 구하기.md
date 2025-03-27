### 🔗 월별 잡은 물고기 수 구하기
https://school.programmers.co.kr/learn/courses/30/lessons/293260

### ❓ 풀이 방법
MONTH 함수로 달을 추출해 COUNT 함수로 월별 잡은 물고기 수를 계산했다.

### 💡소스 코드
````sql
SELECT COUNT(ID) AS FISH_COUNT, MONTH(TIME) AS MONTH
FROM FISH_INFO
GROUP BY MONTH
ORDER BY MONTH;
````