# 문제 링크 : https://school.programmers.co.kr/learn/courses/30/lessons/299310

## 문제 풀이 
Mysql에서 YEAR을 이용해 DIFFERENTIATION_DATE의 년도, 그리고 MAX를 이용해서 SIZE의 최대값을 구할 수 있습니다.<br/>
GROUP BY를 통해 YEAR에 대한 SIZE의 서브쿼리를 만듭니다.<br/>
이후 JOIN을 이용해 일반 테이블 ECOLI_DATA과, 위의 서브쿼리를 YEAR을 이용해서 INNER JOIN합니다.<br/>
최대 SIZE - 현재 SIZE 으로 편차를 구합니다.<br/>
마지막으로 년도에 대한 오름차순, 편차에 대한 오름차순을 구하면 됩니다.

## 코드
```sql
-- MYSQL로 풀었습니다.
SELECT MAX_SIZE.YEAR_DATE as YEAR, MAX_SIZE.SIZE - NOW.SIZE_OF_COLONY AS YEAR_DEV, NOW.ID FROM ECOLI_DATA NOW
INNER JOIN 
(SELECT YEAR(DIFFERENTIATION_DATE) AS YEAR_DATE, MAX(SIZE_OF_COLONY) AS SIZE
 FROM ECOLI_DATA GROUP BY YEAR(DIFFERENTIATION_DATE)) MAX_SIZE ON YEAR(NOW.DIFFERENTIATION_DATE) = MAX_SIZE.YEAR_DATE
 ORDER BY YEAR, YEAR_DEV
```