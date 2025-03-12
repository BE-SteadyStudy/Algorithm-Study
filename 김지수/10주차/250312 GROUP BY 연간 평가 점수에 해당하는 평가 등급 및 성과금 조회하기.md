### 문제 링크
[연간 평가 점수에 해당하는 평가 등급 및 성과금 조회하기](https://school.programmers.co.kr/learn/courses/30/lessons/284528)

### 풀이 방법
- `HR_EMPLOYEES` 테이블과 `HR_GRADE` 테이블을 `EMP_NO`에 대해 조인한다.
- 레코드를 `EMP_NO`에 대해 그룹화한다.
- `EMP_NO`, `EMP_NAME`, `GRADE`, `BONUS` 칼럼을 조회한다.
    - `GRADE`는 사원별 평균 `SCORE`의 범위에 따라 결정된다.
    - `BONUS`는 사원별 평균 `SCORE`의 범위에 따라 결정된 값에 `SAL`을 곱해 계산한다.
- 레코드를 `EMP_NO`에 대해 오름차순 정렬한다.

### 소스 코드
```sql
SELECT EMP.EMP_NO, EMP_NAME,
       (CASE
           WHEN AVG(SCORE) >= 96 THEN 'S'
           WHEN AVG(SCORE) >= 90 THEN 'A'
           WHEN AVG(SCORE) >= 80 THEN 'B'
           ELSE 'C'
       END) AS GRADE,
       SAL * (CASE
                 WHEN AVG(SCORE) >= 96 THEN 0.2
                 WHEN AVG(SCORE) >= 90 THEN 0.15
                 WHEN AVG(SCORE) >= 80 THEN 0.1
                 ELSE 0
             END) AS BONUS
FROM HR_EMPLOYEES AS EMP
JOIN HR_GRADE AS GRADE
ON EMP.EMP_NO = GRADE.EMP_NO
GROUP BY EMP.EMP_NO
ORDER BY EMP.EMP_NO
```