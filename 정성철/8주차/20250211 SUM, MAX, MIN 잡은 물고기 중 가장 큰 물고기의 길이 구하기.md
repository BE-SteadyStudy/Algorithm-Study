# 문제 링크 : https://school.programmers.co.kr/learn/courses/30/lessons/298515

## 문제 풀이 
MAX(LENGTH)를 이용해 최대 길이를 구할 수 있고, CONCAT을 이용하면 문자열을 합칠 수 있으므로 cm를 붙일 수 있습니다.

## 코드
```sql
-- MYSQL로 풀었습니다.
SELECT CONCAT(MAX(LENGTH), 'cm') as MAX_LENGTH FROM FISH_INFO
```