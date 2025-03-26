### 🔗 카테고리 별 도서 판매량 집계하기
https://school.programmers.co.kr/learn/courses/30/lessons/144855

### ❓ 풀이 방법
YEAR과 MONTH 함수로 2022년 1월 데이터만 골랐다.

### 💡소스 코드
````sql
SELECT B.CATEGORY, SUM(S.SALES) AS TOTAL_SALES
FROM BOOK_SALES S
         JOIN BOOK B ON S.BOOK_ID=B.BOOK_ID
WHERE YEAR(S.SALES_DATE)=2022 AND MONTH(S.SALES_DATE)=01
GROUP BY B.CATEGORY
ORDER BY B.CATEGORY;
````