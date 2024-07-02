---
layout: post
title: "[Spring] Spring MVC Project가 안 뜨는 문제 해결 방법"
date: 2024-07-01 12:07 +0900
description: Spring MVC Project가 안 뜨는 문제 해결 방법
category: [ISSUE]
tags: [STS, Spring, 스프링, MVC]
---
## Spring MVC Project 템플릿이 안 보이는 문제
### 이슈
스프링 공부를 하기 위해 STS를 설치하고 스프링 레거시 프로젝트로 Spring MVC Project 템플릿을 사용하려고 했는데 아래 이미지처럼 Simple Projects만 있었다.
<br/>
![img](https://github.com/kbyunghoon/kbyunghoon.github.io/assets/79817983/ce11f9af-e70f-48ea-a06e-0e739fa28884)

구글링을 하여 찾아보니 올해 2월쯤부터 3.0 xml을 다운로드 할 수 없는 문제가 생겨 안 뜬다고한다.

그래서 해결 방법 모두 시도해보다 해결 방법을 찾았다.

### 해결 방법
1. 해당 워크스페이스 경로로 들어간다.
2. 숨은 폴더를 보이게 설정하면 아래와 같은 폴더가 보인다.
	- MAC : ( Shift + Command + .(점) )
	- 윈도우10 기준 : 파일탐색기 상단 `보기` -> `옵션` -> `보기` 탭 -> `숨김 파일, 폴더 및 드라이브 표시` 체크 -> 적용
  <br/> ![img](https://github.com/kbyunghoon/kbyunghoon.github.io/assets/79817983/ea817d1b-293d-4af7-bf9a-27b87dc1b0b4)

3. 아래의 파일을 해당 폴더에 맞게 넣어준다.
	- xml파일(<a id="download-link" href="/assets/file/https-content.xml" download>다운로드</a>)<br/> `/워크스페이스폴더/.metadata/.plugins/org.springsource.ide.eclipse.commons.content.core`

<br/>
![img](https://github.com/kbyunghoon/kbyunghoon.github.io/assets/79817983/aa7eacc4-e5d6-4a91-b27e-1e838c4ab7ba)

- STS를 껐다 키면 정상적으로 보인다.<br/>
![img](https://github.com/kbyunghoon/kbyunghoon.github.io/assets/79817983/78a87a08-7e9a-4c4b-aa16-02bb1486d5f5)