### 문제 링크
[고양이와 개는 몇 마리 있을까](https://school.programmers.co.kr/learn/courses/30/lessons/59040)

### 풀이 방법
- `ANIMAL_INS` 테이블에서 `ANIMAL_TYPE`을 기준으로 그룹화한다.
- `ANIMAL_TYPE` 칼럼과 `COUNT(ANIMAL_TYPE)` 칼럼을 조회한다.
- Cat을 Dog보다 먼저 조회해야 하므로 `ANIMAL_TYPE`에 대해 오름차순으로 정렬한다.

### 소스 코드
```sql
SELECT ANIMAL_TYPE, COUNT(ANIMAL_TYPE) AS count
FROM ANIMAL_INS 
GROUP BY ANIMAL_TYPE
ORDER BY ANIMAL_TYPE
```