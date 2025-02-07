### 문제 링크
[동물 수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/59406)

### 풀이 방법
- ANIMAL_INS 테이블에서 ANIMAL_ID가 NULL이 아닌 레코드의 개수를 조회한다.
- 별칭을 count로 지정한다.

### 소스 코드
```sql
SELECT COUNT(ANIMAL_ID) AS count
FROM ANIMAL_INS
```