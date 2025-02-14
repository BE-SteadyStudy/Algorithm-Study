### 🔗 연도별 대장균 크기의 편차 구하기
https://school.programmers.co.kr/learn/courses/30/lessons/299310

### ❓ 풀이 방법
연도별 가장 큰 개체 크기를 서브 쿼리로 구하고
ECOLI_DATA와 JOIN해서 각 개체의 연도별 크기 편차를 구했다.

### 💡소스 코드
````sql
SELECT YEAR(E.DIFFERENTIATION_DATE) YEAR, (MS.MAX_SIZE - E.SIZE_OF_COLONY) AS YEAR_DEV, E.ID
FROM ECOLI_DATA E
    LEFT JOIN (
    SELECT MAX(SIZE_OF_COLONY) 'MAX_SIZE', DATE_FORMAT(DIFFERENTIATION_DATE, '%Y') YEAR
    FROM ECOLI_DATA
    GROUP BY DATE_FORMAT(DIFFERENTIATION_DATE, '%Y')
    ) MS
ON YEAR(E.DIFFERENTIATION_DATE)=MS.YEAR
ORDER BY YEAR, YEAR_DEV;
````