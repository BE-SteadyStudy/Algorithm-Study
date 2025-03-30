### 문제 링크
[ROOT 아이템 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/273710)

### 풀이 방법
- `ITEM_INFO` 테이블과 `ITEM_TREE` 테이블을 `ITEM_ID` 칼럼에 대해 조인한다.
- `PARENT_ITEM_ID`가 `NULL`인 레코드만 남긴다.
- `ITEM_ID`, `ITEM_NAME` 칼럼을 선택한다.
- `ITEM_ID`에 대해 오름차순 정렬한다.

### 소스 코드
```sql
SELECT ITEM_INFO.ITEM_ID, ITEM_NAME
FROM ITEM_INFO 
JOIN ITEM_TREE 
ON ITEM_INFO.ITEM_ID = ITEM_TREE.ITEM_ID
WHERE PARENT_ITEM_ID IS NULL
ORDER BY ITEM_ID
```