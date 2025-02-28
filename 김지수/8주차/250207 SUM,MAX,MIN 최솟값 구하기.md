### 문제 링크
[최솟값 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/59038)

### 풀이 방법
- ANIMAL_INS 테이블에서 DATETIME 칼럼의 최솟값을 조회한다.
- 별칭을 '시간'으로 지정한다.

### 소스 코드
```sql
SELECT MIN(DATETIME) AS 시간
FROM ANIMAL_INS 
```