### 문제 링크
[특정 조건을 만족하는 물고기별 수와 최대 길이 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/298519)

### 풀이 방법
- `FISH_INFO` 테이블의 레코드들을 `FISH_TYPE`에 대해 그룹화한다.
- `LENGTH`가 `NULL`인 경우 10으로 치환 후 그룹별 `LENGTH`의 평균이 33 미만인 레코드들을 제외한다.
- `FISH_COUNT`, `MAX_LENGTH`, `FISH_TYPE`를 조회한다.
    -  `FISH_COUNT`는 `count(FISH_TYPE)`이고, `MAX_LENGTH`는 `max(LENGTH)`이다.
- `FISH_TYPE`에 대해 오름차순 정렬한다.

### 소스 코드
```sql
select count(FISH_TYPE) as FISH_COUNT, 
       max(LENGTH) as MAX_LENGTH, 
       FISH_TYPE
from FISH_INFO
group by FISH_TYPE
having avg(case
                when LENGTH IS NULL then 10
                else LENGTH
           end) >= 33
order by FISH_TYPE
```