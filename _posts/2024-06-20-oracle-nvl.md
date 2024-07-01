---
layout: post
title: "[오라클] NVL 함수"
date: 2024-06-20 14:16 +0900
description: 오라클 NVL 함수
category: [SQL]
tags: [ORACLE,오라클]
---
## NVL함수란?
- <span style="background-color:#fff5b157">Oracle 데이터베이스에서 제공하는 함수</span>로, 지정된 열이나 표현식이 `NULL`인 경우 **원하는 대체 값으로 반환하고 싶을 때** 사용되는 함수
- `NULL` 값을 처리할 때 유용하며, 데이터베이스 쿼리에서 `NULL` 값을 다룰 때 자주 사용된다.

### 문법

```sql
NVL(expression, replacement_value)
```

-   `expression`: `NULL` 여부를 확인할 열 또는 표현식으로 지정값을 의미한다.
-   `replacement_value`: `expression`이 **`NULL`일 때** 반환할 값

### 사용 방법

| WAREHOUSE_ID | WAREHOUSE_NAME | ADDRESS | TLNO | FREEZER_YN |
|---|---|---|---|---|
| WH001 | Warehouse A | 경기도 수원시 팔달구 | 010-1234-5678 | Y |
| WH002 | Warehouse B | 경기도 고양시 덕양구 | 010-2345-6789 | NULL |
| WH003 | Warehouse C | 서울특별시 강남구 | 010-3456-7890 | N |
| WH004 | Warehouse D | 경기도 성남시 분당구 | 010-4567-8901 | NULL |
| WH005 | Warehouse E | 부산광역시 해운대구 | 010-5678-9012 | Y |

위의 `FOOD_WAREHOUSE` 테이블이 있다고 가정해본다.
- `FOOD_WAREHOUSE` 테이블에서 창고의 ID, 이름, 냉동시설 여부를 조회하고 싶다면 냉동시설 여부가 `NULL`인 경우, `NVL` 함수를 사용하여 'N'으로 출력이 가능하다.

- 코드

```sql
SELECT WAREHOUSE_ID, 
       WAREHOUSE_NAME, 
       NVL(FREEZER_YN, 'N') AS FREEZER_YN
FROM FOOD_WAREHOUSE
```

| WAREHOUSE_ID | WAREHOUSE_NAME | FREEZER_YN |
|---|---|---|
| WH001 | Warehouse A | Y |
| WH002 | Warehouse B | N |
| WH003 | Warehouse C | N |
| WH004 | Warehouse D | N |
| WH005 | Warehouse E | Y |

위와 같은 결과가 나온다. 이렇게 값이 `NULL`인 경우를 다룰 때 원하는 값으로 반환이 가능하다.
