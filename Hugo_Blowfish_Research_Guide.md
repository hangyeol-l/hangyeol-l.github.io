# Hugo + Blowfish 연구 홈페이지 가이드

> Robotics Research Website (GitHub Pages)

## Hugo 프로젝트 구조

``` text
project/
├── archetypes/
├── assets/
├── content/
├── data/
├── i18n/
├── layouts/
├── public/
├── static/
├── themes/
├── hugo.toml
```

------------------------------------------------------------------------

# 가장 중요한 폴더

## 1. content/

블로그 글과 프로젝트를 작성하는 곳이다.

예시

``` text
content/
├── posts/
│   ├── research-log/
│   ├── paper-review/
│   ├── github-analysis/
│   ├── control-theory/
│   └── reinforcement-learning/
│
├── projects/
│   ├── isaac-lab/
│   ├── meal-assist/
│   ├── pediatric-robot/
│   └── humanoid/
│
└── about/
```

각 글은 하나의 폴더(Page Bundle)를 사용하는 것을 추천한다.

``` text
content/
└── paper-review/
    └── ocs2-legged-control/
        ├── index.md
        ├── cover.png
        ├── architecture.png
        ├── qp.png
        └── walking.gif
```

`index.md`

``` markdown
---
title: OCS2 Review
date: 2026-07-01
draft: false
tags:
- MPC
- OCS2
categories:
- Paper Review
---

# OCS2

![Architecture](architecture.png)

![Walking](walking.gif)
```

이미지는 파일 이름만 적으면 된다.

------------------------------------------------------------------------

## 2. static/

사이트 전체에서 공통으로 사용하는 파일.

``` text
static/
├── images/
├── videos/
├── pdf/
└── profile/
```

사용 예시

``` markdown
![](/images/profile.png)
```

------------------------------------------------------------------------

## 3. themes/

Blowfish 테마가 들어있는 폴더.

``` text
themes/
└── blowfish/
```

가능하면 수정하지 않는다.

------------------------------------------------------------------------

## 4. hugo.toml

사이트 전체 설정.

``` toml
title = "Han"
theme = "blowfish"
baseURL = "https://username.github.io/"
```

------------------------------------------------------------------------

## 5. public/

Hugo가 HTML로 빌드한 결과가 저장된다.

``` text
content/
        ↓
     hugo
        ↓
public/
```

직접 수정하지 않는다.

------------------------------------------------------------------------

# 거의 사용하지 않는 폴더

## assets/

SCSS, CSS, JavaScript 등을 관리.

## layouts/

HTML 템플릿.

## archetypes/

새 글의 기본 템플릿.

## data/

YAML / JSON 데이터.

## i18n/

다국어 지원.

------------------------------------------------------------------------

# 추천 디렉터리 구조

``` text
content/

├── posts/
│   ├── research-log/
│   ├── paper-review/
│   ├── github-analysis/
│   ├── control-theory/
│   └── reinforcement-learning/
│
├── projects/
│   ├── isaac-lab/
│   ├── meal-assist/
│   ├── pediatric-robot/
│   └── whole-body-mpc/
│
└── about/
```

------------------------------------------------------------------------

# 글 생성

``` bash
hugo new posts/research-log/isaac-lab/index.md
```

------------------------------------------------------------------------

# 실행

``` bash
hugo server
```

브라우저

``` text
http://localhost:1313
```

------------------------------------------------------------------------

# 빌드

``` bash
hugo
```

빌드 결과는 `public/`에 생성된다.

------------------------------------------------------------------------

# 연구 홈페이지 운영 팁

프로젝트별로 하나의 폴더(Page Bundle)를 유지하는 것을 추천한다.

``` text
meal-assist/
├── index.md
├── robot.jpg
├── result.png
├── trajectory.gif
└── video.mp4
```

이 방식이면 글과 이미지, GIF, 동영상을 함께 관리할 수 있다.

------------------------------------------------------------------------

# 앞으로 추천할 메뉴

-   Home
-   Projects
-   Research Log
-   Paper Review
-   GitHub Analysis
-   About

이 구조를 유지하면 연구 기록, 논문 분석, GitHub 코드 분석을 체계적으로
관리할 수 있다.
