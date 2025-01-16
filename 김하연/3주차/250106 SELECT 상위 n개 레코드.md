❓ 문제
---

[상위 n개 레코드](https://school.programmers.co.kr/learn/courses/30/lessons/59405)

### 문제 설명

`ANIMAL_INS` 테이블은 `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE`로 이루어져 있고,
각각 동물의 아이디, 생물 종, 보호 시작일, 보호 시작 시 상태, 이름, 성별 및 중성화 여부를 나타냅니다.

### 문제

동물 보호소에 가장 먼저 들어온 동물의 이름을 조회하는 SQL 문을 작성해주세요.

### 예시

ANIMAL_INS 테이블이 다음과 같다면

|ANIMAL_ID	|ANIMAL_TYPE	|DATETIME	|INTAKE_CONDITION	|NAME	|SEX_UPON_INTAKE|
|---|---|---|---|---|---|
|A399552	|Dog	|2013-10-14 15:38:00	|Normal	|Jack	|Neutered Male|
|A379998	|Dog	|2013-10-23 11:42:00	|Normal	|Disciple	|Intact Male|
|A370852	|Dog	|2013-11-03 15:04:00	|Normal	|Katie	|Spayed Female|
|A403564	|Dog	|2013-11-18 17:03:00	|Normal	|Anna	|Spayed Female|

SQL문을 실행하면 다음과 같이 나와야 합니다.

|NAME|
|----|
|Jack|

<br/>
<br/>

💡 풀이
---

`DATETIME`을 기준으로 오름차순 정렬 후 첫번째 행만 선택

<br/>
<br/>

💻 코드
---

```sql
SELECT
	NAME
FROM
	ANIMAL_INS
ORDER BY
	DATETIME
LIMIT
	1;
```
