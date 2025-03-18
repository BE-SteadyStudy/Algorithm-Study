### 문제 링크
[언어별 개발자 분류하기](https://school.programmers.co.kr/learn/courses/30/lessons/276036)

### 풀이 방법
- 프론트엔드 기술 코드들을 전부 합한 공통 테이블 `FRONTEND`를 만든다.
- C# 기술 코드를 구하는 공통 테이블 `CSHARP`을 만든다.
- Python 기술 코드를 구하는 공통 테이블 `PYTHON`을 만든다.
- 개발자들을 조건에 맞게 `GRADE`로 분류한다. 어느 조건에도 속하지 않는 경우 `NULL`로 지정한다.
- `GRADE`가 `NULL`인 레코드를 제외한다.

### 소스 코드
```sql
WITH FRONTEND AS ( -- 프론트엔드 기술 코드 --
    SELECT SUM(CODE) AS CODE
    FROM SKILLCODES
    WHERE CATEGORY = 'Front End'
), CSHARP AS ( -- C# 기술 코드 --
    SELECT CODE
    FROM SKILLCODES
    WHERE NAME = 'C#'
), PYTHON AS ( -- Python 기술 코드 --
    SELECT CODE
    FROM SKILLCODES
    WHERE NAME = 'Python'
)

SELECT
    CASE
        WHEN DEV.SKILL_CODE & FRONTEND.CODE AND DEV.SKILL_CODE & PYTHON.CODE THEN 'A'
        WHEN DEV.SKILL_CODE & CSHARP.CODE THEN 'B'
        WHEN DEV.SKILL_CODE & FRONTEND.CODE THEN 'C'
        ELSE NULL
    END AS GRADE,
    ID,
    EMAIL
FROM DEVELOPERS AS DEV, FRONTEND, PYTHON, CSHARP
HAVING GRADE IS NOT NULL
ORDER BY GRADE, ID
```