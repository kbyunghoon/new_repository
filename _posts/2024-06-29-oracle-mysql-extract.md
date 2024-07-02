---
layout: post
title: "[오라클/MySQL] EXTRACT 함수"
date: 2024-06-29 15:01 +0900
description: 오라클 MySQL EXTRACT 함수
category: [SQL]
tags: [ORACLE, 오라클, MySQL, SQL]
---
## EXTRACT 함수
### EXTRACT 함수란?
오라클과 MySQL에서 날짜 또는 시간 값에서 특정 부분(예: 연도, 월, 일, 시간 등)을 추출할 때 사용된다.

### 예시
```sql
EXTRACT(unit FROM date)
```
- `unit` : 추출할 날짜 또는 시간의 부분
	-   `YEAR`: 년
	-   `MONTH`: 월
	-   `DAY`: 일
	-   `HOUR`: 시
	-   `MINUTE`: 분
	-   `SECOND`: 초
- `date` : 날짜 또는 시간 값.

#### 연도 추출
```sql
SELECT EXTRACT(YEAR FROM '2024-06-29') AS year;
```

#### 월 추출
```sql
SELECT EXTRACT(MONTH FROM '2024-06-29') AS month;
```

#### 일 추출
```sql
SELECT EXTRACT(DAY FROM '2024-06-29') AS day;
```
