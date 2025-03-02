### 문제 링크
[동명 동물 수 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/59041)

### 풀이 방법
- `ANIMAL_INS` 테이블에서 레코드들을 `NAME`을 기준으로 그룹화한다.
- `COUNT(NAME)`의 값이 2 이상인 결과만 필터링한다.
- `NAME` 칼럼과 `COUNT(NAME)` 칼럼을 조회한다.
- `NAME`에 대해 오름차순으로 정렬한다.

### 소스 코드
```sql
SELECT NAME, COUNT(NAME) AS COUNT
FROM ANIMAL_INS 
GROUP BY NAME
HAVING COUNT(NAME) >= 2
ORDER BY NAME
```