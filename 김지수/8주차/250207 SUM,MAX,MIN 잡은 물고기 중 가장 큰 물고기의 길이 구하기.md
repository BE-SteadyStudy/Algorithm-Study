### 문제 링크
[잡은 물고기 중 가장 큰 물고기의 길이 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/298515)

### 풀이 방법
- FISH_INFO 테이블에서 LENGTH 칼럼의 최댓값을 조회한다.
- LENGTH의 값 뒤에 'cm'을 붙인다.
- 별칭을 MAX_LENGTH로 지정한다.

### 소스 코드
```sql
SELECT CONCAT(MAX(LENGTH), 'cm') AS MAX_LENGTH
FROM FISH_INFO 
```