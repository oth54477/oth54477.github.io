# th-oh.site — 오태훈 포트폴리오 겸 개인 페이지 Design System

<!-- design-md:section experience -->
## 1. Experience

<!-- design-md:claim scope kind=product-surface lang=en -->
### Scope

측정으로 검증한 프론트엔드 플랫폼 엔지니어링 이력을, 채용 담당자와 엔지니어링 리더가 스크롤 한 번으로 판정할 수 있게 제시하는 단일 페이지.
<!-- design-md:claim-end -->

<!-- design-md:claim primary-tasks kind=user-outcomes count=5 lang=en -->
### Primary tasks

- 히어로에서 대표 성과 수치 네 건을 즉시 확인한다

- 케이스마다 문제 · 접근 · 결과 순서로 읽고 판단 근거를 본다

- '자세히'를 펼쳐 구조도와 규명 과정, 철회 기록까지 확인한다

- 인쇄해 같은 내용을 라이트 팔레트 PDF 이력서로 받는다

- 연락처에서 GitHub과 이메일로 이동한다
<!-- design-md:claim-end -->

### Design direction

- 다크 단일 테마에 앰버 악센트 하나. 테마 토글을 두지 않는다

- 위계는 크기가 만든다. 굵기로 소리치지 않는다

- 앰버는 측정값과 상호작용 상태에만 배급한다

- 그림자 없이 여백과 1px 경계선으로만 층위를 만든다

- 히어로 배경은 장식이 아니라 이 페이지가 다루는 주제(Host ↔ Remote 연합 구조) 자체를 그린다

### Principles

- 주장보다 측정값을 앞세운다. 수치가 없으면 강조하지 않는다

- 채택한 조치만큼 철회한 조치도 기록한다

- 도구의 오탐과 자신의 진단 오류까지 실측으로 정정한 과정을 남긴다

- 화면과 인쇄는 같은 문서다. 섹션을 추가하면 인쇄 규칙도 같이 갱신한다

### Avoid

- 라이트/다크 테마 토글

- 그림자 기반 입체 표현

- 굵기로 만드는 위계

- 수치가 없는 서술 문장에 거는 강조

- 빌드 스텝이나 번들러를 요구하는 의존성 추가

<!-- design-md:section foundations -->
## 2. Foundations

<!-- design-md:claim foundations kind=rules-or-constraints lang=en -->
### Semantic tokens

- **color.accent**: `#f0a742` — 단 하나의 악센트. 측정값과 상호작용 상태에만 쓴다
- **color.accent-dim**: `rgba(240, 167, 66, 0.14)` — 앰버의 저채도 배경 변형
- **color.bg**: `#0e1116` — 페이지 바탕. 순검정이 아닌 미세한 청색 기운의 니어블랙
- **color.faint**: `#7c8593` — 섹션 라벨, eyebrow, dt 라벨, 캡션. 앰버에서 물러난 자리를 이 색이 받는다
- **color.line**: `#242c37` — 섹션 구분선과 컴포넌트 테두리. 층위는 이 1px 선이 만든다
- **color.muted**: `#97a1ad` — 부연 설명, 자세히 요약, 칩 라벨
- **color.surface**: `#151a21` — 칩·코드 블록 등 바탕에서 한 단 올라온 면
- **color.text**: `#e9edf2` — 본문과 제목의 기본 글자색
- **font.body**: `"Noto Sans KR", "Inter", -apple-system, "Apple SD Gothic Neo", sans-serif` — 한글 본문과 제목
- **font.mono**: `"Space Grotesk", ui-monospace, "SF Mono", monospace` — 수치, 영문 라벨, 칩, 코드
- **layout.case-columns**: `232px 1fr` — 케이스 2단 그리드. 좌측은 라벨과 대표 수치
- **layout.case-gap**: `56px` — 케이스 2단 사이 간격
- **layout.gutter**: `28px` — 컨테이너 좌우 여백
- **layout.max-width**: `1100px` — 본문 컨테이너 최대 폭
- **layout.section-gap**: `88px` — 케이스 섹션 상하 패딩
- **radius.block**: `4px` — 코드 블록
- **radius.chip**: `3px` — 태그 칩과 케이스 링크
- **radius.focus**: `2px` — 포커스 링 모서리

### Contrast pairs

- color.text on color.bg: minimum 4.5:1
- color.muted on color.bg: minimum 4.5:1
- color.faint on color.bg: minimum 4.5:1
- color.accent on color.bg: minimum 4.5:1
- color.muted on color.surface: minimum 4.5:1

### Reduced motion

Required.

### Foundation rules

- 악센트(color.accent)는 측정값, 링크, hover, focus-visible, 다이어그램 내부 데이터 신호에만 쓴다. 장식 라벨에는 쓰지 않는다

- 층위는 color.surface와 color.line 1px로만 만든다. box-shadow와 text-shadow를 쓰지 않는다

- 본문에서 물러난 텍스트는 color.muted, 라벨은 color.faint를 쓴다

- 인쇄에서는 :root를 라이트 팔레트로 교체하고 악센트를 #a15c00으로 낮춘다
<!-- design-md:claim-end -->

<!-- design-md:section typography-assets -->
## 3. Typography & Assets

### Type roles

| Role | Usage | Family | Size | Weight | Line height | Tracking |
|---|---|---|---|---|---|---|
| hero-title | 히어로 h1. 페이지의 논지 한 문장 | font.body | clamp(34px, 6.6vw, 78px) | 400 | 1.16 | -0.03em |
| section-title | 케이스 제목 h2 | font.body | clamp(26px, 3.4vw, 42px) | 400 | 1.25 | -0.022em |
| body | 본문 | font.body | 16px | 400 | 1.75 |  |
| measurement | 본문 안의 측정값 강조(.m)와 리스트 항목 제목(strong) | font.body | 15px | 600 |  |  |
| hero-metric | 히어로 대표 수치 | font.mono | clamp(21px, 2.1vw, 27px) | 700 |  |  |
| case-stat | 케이스 좌단 대표 수치. 케이스당 하나뿐인 앰버 앵커 | font.mono | 26px | 700 |  |  |
| eyebrow | 히어로 상단 직무 라벨 | font.mono | 12px | 400 |  | 0.18em |
| section-label | 케이스 좌단 분류 라벨과 dt 라벨 | font.mono | 12px | 400 |  | 0.12em |
| disclosure | '자세히' 토글 요약 | font.mono | 13px | 400 |  | 0.06em |
| chip | 기술 스택 칩과 케이스 링크 | font.mono | 12.5px | 400 |  |  |
| print-hero-title | 인쇄 h1. 화면용 clamp를 상속하면 A4에서 52px가 되어 본문 대비가 무너진다 | font.body | 26px | 600 | 1.3 | -0.01em |
| print-section-title | 인쇄 h2. 고정하지 않으면 A4에서 h1보다 커져 위계가 뒤집힌다 | font.body | 17px | 600 | 1.35 | -0.01em |

### Assets

| Asset | Kind | Source status | License status | Source | Notes |
|---|---|---|---|---|---|
| noto-sans-kr | font | official | verified | Google Fonts (SIL Open Font License 1.1). wght 400;500;600;700 | 한글 본문과 제목. 600은 측정값 강조 전용으로 요청한다 — 링크에서 빠지면 CSS 폰트 매칭이 700으로 떨어져 강조가 무력화된다 |
| space-grotesk | font | official | verified | Google Fonts (SIL Open Font License 1.1). wght 500;700 | 수치·영문 라벨·칩·코드 |

### Rules

- 제목의 위계는 크기가 만든다. hero-title과 section-title은 모두 weight 400을 쓴다

- 700은 측정값 계열(hero-metric, case-stat)과 다이어그램 내부 라벨에만 남긴다

- 본문 강조는 .m과 strong 모두 weight 600으로 통일한다

- 화면용 clamp는 인쇄에서 vw가 A4 폭으로 재해석되므로, 인쇄 제목은 고정 px로 다시 선언한다

<!-- design-md:section components-states -->
## 4. Components & States

### Component: hero-metric

**Semantics:** 히어로 상단의 대표 성과 네 건. 페이지에서 가장 굵은 요소이며 의도된 데이터 앵커다

- Anatomy: 수치, 단위, 라벨
- States: default
- Token references: font.mono, color.text, color.faint

- Interaction kind: non-interactive
- Interaction reason: 표시 전용 수치 블록으로 클릭·포커스 대상이 아니다

### Component: federation-field

**Semantics:** 히어로 배경에 Host ↔ Remote 런타임 연합 구조를 2D 캔버스 원근 투영으로 그린다. 본문 텍스트 하단 기준으로 띠를 잡고, 띠가 100px 미만이거나 뷰포트가 640px 미만이면 그리지 않는다

- Anatomy: canvas, Host 클러스터, 게이트웨이 노드, 경계면 점선, Remote 클러스터 3, HOST/REMOTES 라벨
- States: default, pointer-tracking, auto-rotate, offscreen-paused, reduced-motion-static, hidden-narrow
- Token references: color.accent, color.muted

- Interaction kind: non-interactive
- Interaction reason: aria-hidden이며 pointer-events가 없다. 포인터 위치를 읽기만 하고 입력을 받지 않는다

### Component: tag-chip

**Semantics:** 기술 스택 항목 표시

- Anatomy: 라벨
- States: default
- Token references: font.mono, color.surface, color.line, color.muted, radius.chip

- Interaction kind: non-interactive
- Interaction reason: 링크나 필터가 아닌 정적 라벨이다

### Component: case-link

**Semantics:** 케이스의 외부 근거로 나가는 링크 칩

- Anatomy: 라벨
- Variants: PR, Issue, 저장소
- States: default, hover, focus-visible
- Token references: font.mono, color.surface, color.line, color.muted, color.accent, radius.chip

- Interaction kind: interactive

#### State applicability

| State | Applicability | Reason |
|---|---|---|
| default | applicable |  |
| hover | applicable |  |
| focus-visible | applicable |  |
| disabled | not-applicable | 정적 문서의 외부 링크로 비활성 상태가 존재하지 않는다 |
| loading | not-applicable | 비동기 요청 없이 문서 이동만 한다 |
| error | not-applicable | 클라이언트에서 처리하는 실패 경로가 없다 |
| success | not-applicable | 완료를 보고할 트랜잭션이 없다 |

### Component: inline-link

**Semantics:** 본문 안 링크. 앰버 글자색과 반투명 앰버 밑줄로 어포던스를 준다

- Anatomy: 텍스트, 하단 경계선
- States: default, hover, focus-visible
- Token references: color.accent, radius.focus

- Interaction kind: interactive

#### State applicability

| State | Applicability | Reason |
|---|---|---|
| default | applicable |  |
| hover | applicable |  |
| focus-visible | applicable |  |
| disabled | not-applicable | 정적 문서의 링크로 비활성 상태가 존재하지 않는다 |
| loading | not-applicable | 비동기 요청 없이 문서 이동만 한다 |
| error | not-applicable | 클라이언트에서 처리하는 실패 경로가 없다 |
| success | not-applicable | 완료를 보고할 트랜잭션이 없다 |

### Component: disclosure

**Semantics:** 케이스의 상세 근거를 감싸는 details/summary. 뷰포트에 들어오면 주변광 하이라이트로 존재를 알리고, 인쇄 시 자동으로 펼쳐진다

- Anatomy: +/− 마커, 요약 문구, 본문
- States: default, collapsed, expanded, hover, focus-visible, in-view
- Token references: font.mono, color.muted, color.accent, color.faint

- Interaction kind: interactive

#### State applicability

| State | Applicability | Reason |
|---|---|---|
| default | applicable |  |
| hover | applicable |  |
| focus-visible | applicable |  |
| disabled | not-applicable | 항상 펼칠 수 있는 정적 콘텐츠다 |
| loading | not-applicable | 내용이 문서에 이미 포함되어 지연 로드가 없다 |
| error | not-applicable | 실패할 수 있는 동작이 없다 |
| success | not-applicable | 완료를 보고할 트랜잭션이 없다 |

### Component: contact-link

**Semantics:** GitHub과 이메일로 나가는 연락처 링크. 클릭 타깃 확보를 위해 상하 패딩을 준다

- Anatomy: 라벨, 값
- States: default, hover, focus-visible
- Token references: color.accent, color.text, radius.focus

- Interaction kind: interactive

#### State applicability

| State | Applicability | Reason |
|---|---|---|
| default | applicable |  |
| hover | applicable |  |
| focus-visible | applicable |  |
| disabled | not-applicable | 정적 문서의 링크로 비활성 상태가 존재하지 않는다 |
| loading | not-applicable | 비동기 요청 없이 문서 이동만 한다 |
| error | not-applicable | 클라이언트에서 처리하는 실패 경로가 없다 |
| success | not-applicable | 완료를 보고할 트랜잭션이 없다 |

### Rules

- 모든 포커스 가능한 요소는 :focus-visible에서 2px 앰버 아웃라인과 3px 오프셋을 받는다

- 상호작용 상태는 색과 경계선으로만 표현한다. 그림자나 크기 변화를 쓰지 않는다

- 이 페이지는 폼과 비동기 요청이 없으므로 disabled/loading/error/success 상태를 정의하지 않는다

<!-- design-md:section layout-platforms -->
## 5. Layout & Platforms

### Responsive constraints

- Minimum supported width: 320px
- Reflow target: 200% zoom

### Layout rules

- 본문은 layout.max-width 1100px 중앙 정렬에 좌우 layout.gutter 28px

- 케이스는 232px 라벨단 + 1fr 본문의 2단 그리드이며 좁은 폭에서 단일 단으로 스택된다

- 코드 블록, 다이어그램, 표는 각자 overflow-x: auto 컨테이너 안에서 스크롤한다. 페이지 본문은 가로로 밀리지 않는다

- 640px 미만에서는 히어로 배경 필드를 그리지 않는다 — 텍스트 아래 띠가 남지 않아 본문을 가로지르고 라벨도 생략되어 의미 전달이 0이다

### Platform: web

- 무빌드 단일 HTML. 번들러와 npm 의존성을 추가하지 않는다
- 외부 의존성은 Google Fonts 스타일시트뿐이다. 애니메이션 라이브러리를 두지 않고 IntersectionObserver와 CSS 전환으로 진입 리빌과 카운트업을 처리한다
- prefers-reduced-motion에서 진입 애니메이션과 전환을 끄고 배경 필드는 정지 프레임 한 장만 그린다
- 인쇄 시 라이트 팔레트로 교체하고 details를 자동으로 펼쳐 PDF 이력서로 쓴다. 새 섹션을 추가하면 @media print 규칙도 함께 갱신한다

<!-- design-md:section content-locales -->
## 6. Content & Locales

### Voice

- 단정형 서술체. 수치를 문장 앞에 둔다

- 성과와 함께 철회·보류한 판단도 같은 비중으로 적는다

- 과장 표현과 형용사 대신 측정 조건과 단위를 쓴다

- 자신의 오진을 감추지 않고 정정 과정을 남긴다

### Terminology

| Term | Preferred form |
|---|---|
| Host | 연합 구조에서 원격 모듈을 소비하는 쪽. 한국어 문장에서도 Host로 표기한다 |
| Remote | 연합 구조에서 모듈을 노출하는 쪽. 한국어 문장에서도 Remote로 표기한다 |
| 자세히 | 케이스의 상세 근거를 여는 토글 라벨. '더보기'나 '펼치기'로 바꾸지 않는다 |

### Locale: ko (supported)

- html lang="ko"이며 본문에 word-break: keep-all을 적용해 어절 단위로 끊는다
- 기술 용어와 제품명은 번역하지 않고 원문으로 둔다
- 수치는 tabular-nums로 세로 정렬을 맞춘다

<!-- design-md:section governance -->
## 7. Governance

<!-- design-md:claim authority kind=project-system lang=en -->
### Authority

This document is the project design contract for the declared scope.
<!-- design-md:claim-end -->

<!-- design-md:claim application-priority order=prompt-fact,repository-fact,system-contract,reference-inspiration lang=en -->
### Application priority

1. Direct user instructions for the requested scope.
2. Repository facts.
3. This system contract.
4. Reference inspiration.
<!-- design-md:claim-end -->

<!-- design-md:claim unknowns policy=absent-at-smallest-unresolved-boundary lang=en -->
### Unknowns

Omit only the smallest unresolved value or group. Do not replace it with a plausible default.
<!-- design-md:claim-end -->

<!-- design-md:claim changes policy=review-record-validate-before-adoption lang=en -->
### Changes

Record, review, and validate changes before adoption.
<!-- design-md:claim-end -->

### Project priority details

1. 접근성(대비, 포커스 가시성, reduced-motion)은 시각적 선호보다 앞선다

2. 인쇄 산출물의 정확성은 화면 장식보다 앞선다

3. 무빌드 단일 HTML 제약은 새 라이브러리 도입 욕구보다 앞선다

### Additional change rules

- 원본은 포트폴리오/오태훈-포트폴리오.html이며 site/index.html은 재조립 산출물이다. 산출물을 직접 고치지 않는다

- 타이포·간격·색을 바꾸면 @media print 규칙에 미치는 영향을 함께 확인한다

- 새 섹션이나 컴포넌트를 추가하면 이 문서의 components_states와 layout_platforms를 같이 갱신한다

### Decision provenance

- /experience/design_direction/1 — prompt-fact; value: "위계는 크기가 만든다. 굵기로 소리치지 않는다"; evidence: 소유자가 refero.design 레퍼런스 6건을 제시하고 이 방향의 적용을 지시했다, h1 700 -> 400, h2 700 -> 400으로 반영(커밋 d7ca19e, daa80d4)
- /experience/design_direction/2 — prompt-fact; value: "앰버는 측정값과 상호작용 상태에만 배급한다"; evidence: 소유자가 앰버 배급 축소를 승인했다, var(--accent) 참조 24 -> 19, 표면 장식 8곳 -> 1곳(커밋 d7ca19e)
- /foundations/tokens — repository-fact; evidence: 포트폴리오/오태훈-포트폴리오.html의 :root 선언에서 직접 추출했다
- /typography_assets/roles — repository-fact; evidence: h1, h2, body, .m, .metric .num, .case-stat-num, .eyebrow, dt, details summary, .tags span 규칙과 @media print 재선언에서 추출했다
- /foundations/rules/1 — repository-fact; value: "층위는 color.surface와 color.line 1px로만 만든다. box-shadow와 text-shadow를 쓰지 않는다"; evidence: 소스에서 box-shadow 0건, text-shadow 0건을 확인했다
- /layout_platforms/minimum_width_px — repository-fact; value: 320; evidence: 320px 뷰포트에서 실제 가로 스크롤이 발생하지 않음을 maxScrollX 0으로 확인했다
- /layout_platforms/reflow_zoom_percent — repository-fact; value: 200; evidence: 1280px 기준 200% 확대에 해당하는 640px 뷰포트에서 maxScrollX 0을 확인했다
- /components_states/components/1 — repository-fact; evidence: #federation-field 캔버스 구현과 640px 미만 display:none, 띠 100px 미만 미출력 가드에서 추출했다
- /content_locales/locales/0 — repository-fact; evidence: html lang="ko", body의 word-break: keep-all, font-variant-numeric: tabular-nums 선언
- /experience/principles/0 — repository-fact; value: "주장보다 측정값을 앞세운다. 수치가 없으면 강조하지 않는다"; evidence: 히어로 h1 문안과 케이스 구성(문제·접근·결과), 본문 강조 .m 18곳이 모두 숫자를 포함하도록 정리한 커밋 7d2cfec, 76dd687
- /typography_assets/assets/0/notes — repository-fact; value: "한글 본문과 제목. 600은 측정값 강조 전용으로 요청한다 — 링크에서 빠지면 CSS 폰트 매칭이 700으로 떨어져 강조가 무력화된다"; evidence: Google Fonts 요청에 600을 추가하기 전에는 CSS 폰트 매칭이 700을 선택해 변경이 무효였다(커밋 1b26de2)
- /governance/change_policy/0 — repository-fact; value: "원본은 포트폴리오/오태훈-포트폴리오.html이며 site/index.html은 재조립 산출물이다. 산출물을 직접 고치지 않는다"; evidence: 두 파일의 차이가 doctype/head/body 래퍼 10줄뿐임을 확인했다
- /experience/avoid/4 — prompt-fact; value: "빌드 스텝이나 번들러를 요구하는 의존성 추가"; evidence: 소유자의 th-oh-design 스킬이 무빌드 단일 HTML과 CDN 전용을 하드 제약으로 규정한다
- /layout_platforms/platforms/0/rules/1 — repository-fact; value: "외부 의존성은 Google Fonts 스타일시트뿐이다. 애니메이션 라이브러리를 두지 않고 IntersectionObserver와 CSS 전환으로 진입 리빌과 카운트업을 처리한다"; evidence: GSAP과 ScrollTrigger CDN 2건을 제거하고 IntersectionObserver + CSS 전환으로 대체했다. scrub 사용처가 없어 rootMargin으로 같은 트리거 경계를 만들 수 있었다
