### 문제 링크
[즐겨찾기가 가장 많은 식당 정보 출력하기](https://school.programmers.co.kr/learn/courses/30/lessons/131123)

### 풀이 방법
- `REST_INFO` 테이블과 서브 쿼리 `MAX_REST_INFO`를 `FOOD_TYPE`과 `FAVORITES`에 대해 조인한다.
- `MAX_REST_INFO`는 각 `FOOD_TYPE`별 `max(FAVORITES)` 값을 가지고 있다.
- `FOOD_TYPE`, `REST_ID`, `REST_NAME`, `FAVORITES`를 조회한다.
- `FOOD_TYPE`에 대해 내림차순 정렬한다.

### 소스 코드
```sql
select REST_INFO.FOOD_TYPE, REST_INFO.REST_ID, REST_INFO.REST_NAME, REST_INFO.FAVORITES
from REST_INFO
join (
    select FOOD_TYPE, max(FAVORITES) as MAX_FAVORITES
    from REST_INFO
    group by FOOD_TYPE
) as MAX_REST_INFO
on REST_INFO.FOOD_TYPE = MAX_REST_INFO.FOOD_TYPE
and REST_INFO.FAVORITES = MAX_REST_INFO.MAX_FAVORITES
order by FOOD_TYPE desc
```