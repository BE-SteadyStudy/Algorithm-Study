### 문제 링크
[년, 월, 성별별 상품 구매 회원 수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/131532)

### 풀이 방법
- `USER_INFO` 테이블과 `ONLINE_SALE` 테이블을 `USER_ID` 칼럼에 대해 조인한다.
- `GENDER`가 `null`인 레코드를 제외한다.
- 구매 연도, 구매 월, 성별에 대해 그룹화한다.
- 구매 연도, 구매 월, 성별과 함께 해당 그룹의 회원 수를 조회한다.
    - 하나의 그룹 내에서 `USER_ID`가 중복될 수 있으므로 `distinct`를 사용한다. 
- 구매 연도, 구매 월, 성별에 대해 오름차순 정렬한다.
    - select절에서 구매 일자를 숫자로 변환하면서 지정한 별칭을 사용한다. 

### 소스 코드
```sql
select cast(year(SALES_DATE) as unsigned) as YEAR, 
       cast(month(SALES_DATE) as unsigned) as MONTH, 
       GENDER, 
       count(distinct USER_INFO.USER_ID) as USERS
from USER_INFO 
join ONLINE_SALE 
on USER_INFO.USER_ID = ONLINE_SALE.USER_ID
where GENDER is not null
group by year(SALES_DATE), month(SALES_DATE), GENDER
order by YEAR, MONTH, GENDER
```