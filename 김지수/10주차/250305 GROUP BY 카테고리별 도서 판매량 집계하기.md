### 문제 링크
[카테고리별 도서 판매량 집계하기](https://school.programmers.co.kr/learn/courses/30/lessons/144855)

### 풀이 방법
- `BOOK` 테이블과 `BOOK_SALES` 테이블을 `BOOK_ID` 칼럼에 대해 조인한다.
- `SALES_DATE` 칼럼의 값이 2022년 1월인 레코드만 필터링한다.
- `CATEGORY` 칼럼을 기준으로 그룹화한다.
- `CATEGORY`, `sum(SALES)`를 조회한다.
- `CATEGORY` 칼럼에 대해 오름차순 정렬한다.

### 소스 코드
```sql
select CATEGORY, sum(SALES) as TOTAL_SALES
from BOOK 
join BOOK_SALES
on BOOK.BOOK_ID = BOOK_SALES.BOOK_ID
where year(SALES_DATE) = 2022
and month(SALES_DATE) = 1
group by CATEGORY
order by CATEGORY
```