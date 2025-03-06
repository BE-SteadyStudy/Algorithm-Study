### 문제 링크
[자동차 대여 기록에서 대여중 / 대여 가능 여부 구분하기](https://school.programmers.co.kr/learn/courses/30/lessons/157340)

### 풀이 방법
- `CAR_RENTAL_COMPANY_RENTAL_HISTORY` 테이블의 레코드를 `CAR_ID`에 대해 그룹화한다.
- `CAR_ID`와 `AVAILABILITY`를 조회한다.
    - 이때, `AVAILABILITY`는 `2022-10-16`이 `START_DATE`와 `END_DATE` 사이에 있는 자동차의 `CAR_ID`를 확인한다.
    - 만약 그룹화된 결과에 조건을 만족하는 `CAR_ID`가 있다면 `대여중`이 되고, 그렇지 않다면 `대여 가능`으로 표시된다.
- `CAR_ID`에 대해 내림차순 정렬한다.

### 소스 코드
```sql
select 
    CAR_ID, 
    case 
        when CAR_ID IN (
            select CAR_ID
            from CAR_RENTAL_COMPANY_RENTAL_HISTORY 
            where '2022-10-16' between START_DATE and END_DATE 
        ) then '대여중'
        else '대여 가능'
    end as AVAILABILITY 
from CAR_RENTAL_COMPANY_RENTAL_HISTORY
group by CAR_ID
order by CAR_ID desc
```