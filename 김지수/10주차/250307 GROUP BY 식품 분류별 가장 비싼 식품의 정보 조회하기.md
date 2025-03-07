### 문제 링크
[식품 분류별 가장 비싼 식품의 정보 조회하기](https://school.programmers.co.kr/learn/courses/30/lessons/131116)

### 풀이 방법
- 서브 쿼리에서 '과자', '국', '김치', '식용유'에 해당하는 식품 분류별 가격의 최댓값을 구한다.
- `FOOD_PRODUCT` 테이블에서 서브 쿼리가 반환한 식품 분류와 가격이 각각 동일한 레코드만 남긴다.
- 식품 분류, 가격, 식품 이름을 조회한다.
- 가격에 대해 내림차순 정렬한다. 

### 소스 코드
```sql
select CATEGORY, PRICE as MAX_PRICE, PRODUCT_NAME
from FOOD_PRODUCT
where (CATEGORY, PRICE) in (
    select CATEGORY, max(PRICE)
    from FOOD_PRODUCT
    where CATEGORY in ('과자', '국', '김치', '식용유')
    group by CATEGORY
)
order by MAX_PRICE desc
```