### 문제 링크
[부서별 평균 연봉 조회하기](https://school.programmers.co.kr/learn/courses/30/lessons/284529)

### 풀이 방법
- `HR_DEPARTMENT` 테이블과 `HR_EMPLOYEES` 테이블을 `DEPT_ID` 칼럼을 기준으로 조인한다.
- `DEPT_ID` 칼럼을 기준으로 그룹화한다.
- `DEPT_ID`, `DEPT_NAME_EN`, `round(avg(SAL))`을 조회한다.
- `round(avg(SAL))`에 대해 내림차순 정렬한다.

### 소스 코드
```sql
select DEPT.DEPT_ID, DEPT_NAME_EN, round(avg(SAL)) as AVG_SAL
from HR_DEPARTMENT as DEPT
join HR_EMPLOYEES as EMP
on DEPT.DEPT_ID = EMP.DEPT_ID
group by DEPT.DEPT_ID
order by AVG_SAL desc
```