### 문제 링크
[월별 잡은 물고기 수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/293260)

### 풀이 방법
- `FISH_INFO` 테이블의 레코드들을 `TIME`의 월 부분을 기준으로 그룹화한다.
- 그룹화된 결과의 개수가 0보다 큰 그룹들만 필터링한다.
- 각 그룹마다 `ID`의 개수와 `TIME`의 월 부분을 조회한다.
- `TIME`의 월 부분을 기준으로 오름차순 정렬한다.

### 소스 코드
```sql
select count(ID) as FISH_COUNT, month(TIME) as MONTH
from FISH_INFO 
group by month(TIME)
having count(ID) > 0
order by MONTH
```