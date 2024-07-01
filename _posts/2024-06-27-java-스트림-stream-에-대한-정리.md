---
layout: post
title: "[JAVA] 스트림(Stream)에 대한 정리"
date: 2024-06-27 11:35 +0900
description: 자바 스트림(Stream)
category: [JAVA]
tags: [JAVA, 스트림, Stream]
---
## Stream()
- 스트림이란?
	- 자바 스트림(Streams)은 자바 8에서 도입된 기능으로, **컬렉션 데이터를 처리**하는 데 유용하며 유연하게 사용이 가능하다.
- 스트림 API는 데이터 소스를 추상화하여 일련의 연산을 통해 데이터를 처리할 수 있게 해준다.

### 스트림의 주요 개념
#### 스트림과 컬렉션의 차이점
- 스트림은 데이터를 저장하지 않는다.
	- 단지 데이터를 가져와 필터링하고 매핑하는 일련의 연산을 나타낸다.
- 데이터 소스로부터 전달되는 **데이터 요소의 연속적인 흐름**을 나타낸다.
- 스트림 연산은 **지연(lazy) 연산**으로, 실제 데이터 처리는 최종 연산이 호출될 때까지 수행되지 않는다.
- 스트림은 **일회용**으로 사용되며, 한 번 사용한 스트림을 다시 사용할 수 없다.

#### 스트림의 장점
### 스트림의 장점
1.  **간결성** : 스트림 API를 사용하면 코드가 간결해지고 가독성이 높아진다.
2.  **병렬 처리**: 스트림은 간단하게 병렬 처리를 구현할 수 있다.
	- 그렇기 때문에 멀티코어 프로세서의 성능을 효율적으로 활용할 수 있다.
3.  **지연 연산**: 중간 연산은 지연되어 필요할 때만 실행되므로 성능을 최적화할 수 있다.

| 특징 | 스트림 | 컬렉션 |
|---|---|---|
| 데이터 저장 여부 | 데이터를 저장하지 않음 | 데이터를 저장함 |
| 데이터 처리 방식 | 함수형 프로그래밍 방식 | 명령형 프로그래밍 방식 |
| 데이터 처리 순서 | 내부 반복 | 외부 반복 |
| 데이터 처리 완료 여부 | 지연 처리 (최종 연산 시 처리) | 즉시 처리 |
| 병렬 처리 | 병렬 처리 지원 | 명시적으로 구현해야 함 |
| 사용 예 | 데이터 필터링, 매핑, 집계 | 데이터 저장 및 접근 |
| 반복 사용 | 한 번만 사용 가능 | 여러 번 사용 가능 |
| 중간 연산 | 지연 연산 | 지원하지 않음 |
| 최종 연산 | 즉시 실행 | 즉시 실행 |


#### 스트림 생성
- 스트림은 다양한 데이터 소스(컬렉션, 배열 등)로부터 생성할 수 있다.

```java
List<String> list = Arrays.asList("a", "b", "c");
Stream<String> stream = list.stream();
Stream<String> parallelStream = list.parallelStream(); // 병렬 스트림
```

### 스트림 연산
#### filter
조건에 맞는 요소만을 포함하는 스트림을 반환한다.
```java
// "a"로 시작하는 요소만 포함하는 새로운 스트림을 생성
Stream<String> filteredStream = stream.filter(s -> s.startsWith("a"));
```

#### map
각 요소를 함수에 적용하여 변환된 요소로 구성된 스트림을 반환한다.
```java
Stream<Integer> lengths = stream.map(String::length);
```

#### sorted
스트림 요소를 정렬된 순서로 반환한다.
```java
Stream<String> sortedStream = stream.sorted();
```

#### collect
스트림 요소를 컬렉션이나 다른 형태로 변환한다.
```java
List<String> list = stream.collect(Collectors.toList());
```
#### reduce
스트림 요소를 하나의 결과로 합친다.
```java
int sum = stream.reduce(0, Integer::sum);
```

#### forEach
스트림의 각 요소를 순회하며 주어진 동작을 수행한다.
```java
stream.forEach(System.out::println);
```

#### count
스트림의 요소 개수를 반환한다.
```java
long count = stream.count();
```