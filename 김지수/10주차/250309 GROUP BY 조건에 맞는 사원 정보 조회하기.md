### 문제 링크
[조건에 맞는 사원 정보 조회하기](https://school.programmers.co.kr/learn/courses/30/lessons/284527)

### 풀이 방법
- `HR_EMPLOYEES` 테이블과 `HR_GRADE` 테이블을 `EMP_NO`에 대해 조인한다.
- `EMP_NO`에 대해 그룹화한다.
- `SCORE`의 합, `EMP_NO`, `EMP_NAME`, `POSITION`, `EMAIL`을 조회한다.
- `SCORE`의 합에 대해 내림차순 정렬한다.
- 최상위 레코드를 조회한다.

### 소스 코드
```sql
select sum(SCORE) as SCORE, 
       HR_EMPLOYEES.EMP_NO, 
       EMP_NAME, 
       POSITION, 
       EMAIL
from HR_EMPLOYEES 
join HR_GRADE 
on HR_EMPLOYEES.EMP_NO = HR_GRADE.EMP_NO
group by HR_EMPLOYEES.EMP_NO
order by SCORE desc
limit 1
```