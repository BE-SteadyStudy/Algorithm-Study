### 문제 링크
[진료과별 총 예약 횟수 출력하기](https://school.programmers.co.kr/learn/courses/30/lessons/132202)

### 풀이 방법
- `APPOINTMENT` 테이블에서 `APNT_YMD` 값이 2022년 5월인 레코드를 필터링한다.
- `MCDP_CD`를 기준으로 그룹화한다.
- `MCDP_CD` 칼럼과 `COUNT(MCDP_CD)` 칼럼을 조회한다.
- `COUNT(MCDP_CD)`와 `MCDP_CD`에 대해 순차적으로 오름차순 정렬한다.

### 소스 코드
```sql
SELECT MCDP_CD AS '진료과코드', COUNT(MCDP_CD) AS '5월예약건수'
FROM APPOINTMENT 
WHERE YEAR(APNT_YMD) = 2022 AND MONTH(APNT_YMD) = 5
GROUP BY MCDP_CD
ORDER BY COUNT(MCDP_CD), MCDP_CD
```