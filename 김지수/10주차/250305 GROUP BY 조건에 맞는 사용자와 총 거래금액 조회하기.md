### 문제 링크
[조건에 맞는 사용자와 총 거래금액 조회하기](https://school.programmers.co.kr/learn/courses/30/lessons/164668)

### 풀이 방법
- `USED_GOODS_USER` 테이블과 `USED_GOODS_BOARD` 테이블을 `USER_ID`와 `WRITER_ID`에 대해 조인한다.
- `STATUS`의 값이 `DONE`인 레코드를 필터링한다.
- `USER_ID`에 대해 그룹화한다.
- `PRICE`의 합이 70만 이상인 그룹을 필터링한다.
- `USER_ID`, `NICKNAME`, `sum(PRICE)`를 조회한다.
- `sum(PRICE)`에 대해 오름차순 정렬한다.

### 소스 코드
```sql
select USER_ID, NICKNAME, sum(PRICE) as TOTAL_SALES
from USED_GOODS_USER as USERS
join USED_GOODS_BOARD as BOARD
on USERS.USER_ID = BOARD.WRITER_ID
where STATUS = 'DONE'
group by USER_ID
having sum(PRICE) >= 700000
order by TOTAL_SALES
```