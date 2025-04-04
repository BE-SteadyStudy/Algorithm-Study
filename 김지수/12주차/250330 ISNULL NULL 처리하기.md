### 문제 링크
[NULL 처리하기](https://school.programmers.co.kr/learn/courses/30/lessons/59410)

### 풀이 방법
- `ANIMAL_INS` 테이블에서 `ANIMAL_TYPE`, `NAME`, `SEX_UPON_INTAKE` 칼럼을 선택한다.
    - 이때, `NAME`이 `NULL`이면 `No name`으로 나타낸다. 
- 전체 레코드를 `ANIMAL_ID`에 대해 오름차순 정렬한다.

### 소스 코드
```sql
SELECT ANIMAL_TYPE, IFNULL(NAME, 'No name') AS NAME, SEX_UPON_INTAKE
FROM ANIMAL_INS 
ORDER BY ANIMAL_ID
```