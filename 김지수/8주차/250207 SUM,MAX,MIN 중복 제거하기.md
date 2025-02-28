### 문제 링크
[중복 제거하기](https://school.programmers.co.kr/learn/courses/30/lessons/59408)

### 풀이 방법
- ANIMAL_INS 테이블에서 NAME 칼럼의 중복을 제거한다.
- NAME이 NULL이 아닌 레코드의 개수를 조회한다.
- 별칭을 count로 지정한다.

### 소스 코드
```sql
SELECT COUNT(DISTINCT NAME) AS count
FROM ANIMAL_INS 
```