### 문제 링크
[상위 n개 레코드](https://school.programmers.co.kr/learn/courses/30/lessons/59405)

### 풀이 방법
- ANIMAL_INS 테이블을 DATETIME에 대해 오름차순으로 정렬한다.
- LIMIT 1을 이용해 맨 위의 행 하나를 반환받는다.
- NAME 칼럼을 조회한다.

### 소스 코드
```sql
SELECT NAME
FROM ANIMAL_INS
ORDER BY DATETIME
LIMIT 1
```