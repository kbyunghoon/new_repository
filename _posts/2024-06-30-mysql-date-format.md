---
layout: post
title: "[MySQL] DATE_FORMAT 함수"
date: 2024-06-30 21:29 +0900
description: MySQL DATE_FORMAT 함수
category: [SQL]
tags: [MySQL, SQL]
---

## DATE_FORMAT 함수

### DATE_FORMAT 함수란

- **MySQL**에서 날짜 또는 시간 값을 특정 형식의 문자열로 변환하는 데 사용된다.

  > 오라클에서는 [TO_CHAR()](/posts/oracle-to-char)를 사용하며 해당 설명 게시글을 참고하면 된다.
  {: .prompt-info }

- 날짜와 시간을 다양한 형식으로 표시해야 할 때 유용하다.

### 예시

```sql
DATE_FORMAT(date, format)
```

- `date`는 날짜 또는 시간 값이고, `format`은 출력 형식을 지정하는 문자열이다.

- `format` 문자열에서 사용할 수 있는 형식 지정자- `%Y`: 4자리 연도 (예: 2024)
  - `%y`: 2자리 연도 (예: 24)
  - `%M`: 월 이름 (예: July)
  - `%m`: 2자리 월 (예: 07)
  - `%d`: 2자리 일 (예: 01)
  - `%H`: 2자리 시간 (24시간 형식, 예: 13)
  - `%h`: 2자리 시간 (12시간 형식, 예: 01)
  - `%i`: 2자리 분 (예: 05)
  - `%s`: 2자리 초 (예: 09)
  - `%p`: AM 또는 PM

#### 날짜를 `YYYY-MM-DD` 형식으로 변환

```sql
SELECT DATE_FORMAT('2024-07-01', '%Y-%m-%d') AS DATA;
```

- 결과

|    DATE    |
| :--------: |
| 2024-07-01 |

#### 날짜를 `Month DD, YYYY` 형식으로 변환

```sql
SELECT DATE_FORMAT('2024-07-01', '%M %d, %Y') AS DATE;
```

- 결과

|     DATE      |
| :-----------: |
| July 01, 2024 |

#### 날짜와 시간을 `YYYY-MM-DD HH:MI:SS` 형식으로 변환

```sql
SELECT DATE_FORMAT('2024-07-01 20:00:00', '%Y-%m-%d %H:%i:%s') AS DATE;
```

- 결과

|        DATE         |
| :-----------------: |
| 2024-07-01 20:00:00 |
