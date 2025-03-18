### 문제 링크
[노선별 평균 역 사이 거리 조회하기](https://school.programmers.co.kr/learn/courses/30/lessons/284531)

### 풀이 방법
- `SUBWAY_DISTANCE` 테이블의 레코드들을 `ROUTE`에 대해 그룹화한다.
- `ROUTE`, `TOTAL_DISTANCE`, `AVERAGE_DISTANCE`를 조회한다.
    - `TOTAL_DISTANCE`는 `concat(round(sum(D_BETWEEN_DIST), 1), 'km')`의 별칭이다.
    - `AVERAGE_DISTANCE`는 `concat(round(avg(D_BETWEEN_DIST), 2), 'km')`의 별칭이다.
- `sum(D_BETWEEN_DIST)`에 대해 내림차순 정렬한다.

### 소스 코드
```sql
select ROUTE, 
       concat(round(sum(D_BETWEEN_DIST), 1), 'km') as TOTAL_DISTANCE, 
       concat(round(avg(D_BETWEEN_DIST), 2), 'km') as AVERAGE_DISTANCE
from SUBWAY_DISTANCE 
group by ROUTE
order by sum(D_BETWEEN_DIST) desc
```