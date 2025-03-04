### 문제 링크
[물고기 종류별 잡은 수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/293257)

### 풀이 방법
- `FISH_INFO` 테이블과 `FISH_NAME_INFO` 테이블을 `FISH_TYPE` 칼럼에 대해 조인한다.
- `FISH_NAME` 칼럼에 대해 그룹화한다.
- `COUNT(FISH_NAME)` 값의 별칭을 `FISH_COUNT`로 지정한다.
- `FISH_COUNT`와 `FISH_NAME` 칼럼을 조회한다.
- `FISH_COUNT`에 대해 내림차순 정렬한다.

### 소스 코드
```sql
SELECT COUNT(FISH_NAME) AS FISH_COUNT, FISH_NAME
FROM FISH_INFO 
JOIN FISH_NAME_INFO
ON FISH_INFO.FISH_TYPE = FISH_NAME_INFO.FISH_TYPE
GROUP BY FISH_NAME 
ORDER BY FISH_COUNT DESC
```