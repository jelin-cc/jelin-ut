---
name: jams-design-tokens
description: >
  JAMS 2.1 피그마 디자인 토큰을 코드 변수(Tailwind/CSS/TS)로 제공합니다.
  컬러 팔레트, 시맨틱 컬러(Light/Dark), 타이포그래피, 스페이싱, 그림자, radius,
  테마(JK/AM) 매핑을 포함하는 단일 통합 토큰 시스템입니다.
  MANDATORY TRIGGERS: "JAMS", "잼스", "JAMS2.1", "JAMS 2.1" 포함 모든 요청;
  "피그마 토큰", "디자인 토큰", "design token", "figma token" 언급 시;
  JKblue, AMorange, Pretendard, Brand/primary 등 JAMS 토큰명 언급 시;
  "디자인 시스템에 맞게", "피그마대로", "토큰 적용해서" 표현 시;
  JAMS UI 컴포넌트 코딩, Tailwind config/CSS 변수 설정, 다크모드/라이트모드 매핑,
  컬러 팔레트/색상코드/폰트 사이즈 질문, "primary 색상", "에러 컬러", "Gray/500" 등
  구체적 토큰 값 요청 시;
  icon/color, typography/color, line/color, tag/color 등 시맨틱 토큰 언급 시;
  radius, shadow, spacing, unit 등 레이아웃 토큰 관련 질문 시 반드시 트리거하세요.
---

# JAMS 2.1 Design Tokens

JAMS 2.1 피그마 디자인 시스템의 단일 통합 토큰 레퍼런스입니다.
사용자가 JAMS 관련 디자인 속성을 물어보면, 레퍼런스 파일을 참조해서 정확한 값을 코드로 변환하여 제공합니다.

## Figma Source

- **파일**: 🔒 JAMS 2.1 실험실
- **File Key**: `mrgHPV0VxWmqxV4C8gABgv`
- **URL**: https://www.figma.com/design/mrgHPV0VxWmqxV4C8gABgv/JAMS-2.1

## 토큰 아키텍처

JAMS 2.1은 4개 레이어로 구성됩니다:

1. **Primitive** — 순수 값. 컬러 hex, 유닛 px, 퍼센트 등 변하지 않는 원시값
2. **Semantic (Component)** — Light/Dark 모드에 따라 Primitive를 참조하는 의미론적 토큰 (Bg, Typography, Icon, Line, Box, Shadow, Label 등)
3. **Theme** — JK/AM 테마에 따라 달라지는 브랜드 컬러와 Border Radius
4. **Responsive** — 디바이스별 레이아웃 값

하나의 시맨틱 토큰이 테마(JK→파랑, AM→오렌지)와 모드(Light/Dark)에 따라 자동으로 올바른 Primitive 값을 가리킵니다.

## Reference Files

| 필요한 정보 | 참조 파일 |
|------------|----------|
| 컬러 팔레트 (Gray, Blue, Red, Yellow, Green, Violet, JKblue, AMorange, Opacity, Subway) | `references/primitive-colors.md` |
| 시맨틱 컬러 (Bg, Typography, Icon, Line, Box, Label, Shadow — Light/Dark 매핑) | `references/semantic-tokens.md` |
| 테마 (JK/AM 브랜드 컬러, Border Radius) | `references/theme-tokens.md` |
| 타이포그래피 (폰트, 사이즈 스케일, 행간, 자간, 웨이트) | `references/typography.md` |
| 레이아웃 (Spacing, Radius, Shadow 수치, Unit, Percentage, Responsive) | `references/layout.md` |

## 핵심 토큰 빠른 참조

### 폰트
- **기본 폰트**: Pretendard
- **웨이트**: Regular(400), Medium(500), SemiBold(600), Bold(700)

### 타이포그래피 스케일
| 카테고리 | 범위 | Letter Spacing |
|---------|------|---------------|
| Display (D1~D2) | 48~36px | -0.5px |
| Heading (H1~H5) | 32~18px | -0.5px (H1~H4), 0 (H5) |
| Body (B1~B4) | 17~14px | 0 |
| Caption (C1~C3) | 13~11px | 0 |

### 텍스트 컬러 (시맨틱 — Light 기준)
| 용도 | 토큰 | Primitive | Hex |
|------|------|-----------|-----|
| 기본 텍스트 | Typography/gray950 | Gray/950 | `#1a1a1e` |
| 보조 텍스트 | Typography/gray800 | Gray/800 | `#3e434b` |
| 약한 텍스트 | Typography/gray600 | Gray/600 | `#768091` |
| 비활성 텍스트 | Typography/gray500 | Gray/500 | `#949ba8` |
| 브랜드 텍스트 | Typography/primary | Theme Brand | JK:`#1b55f6` AM:`#ff6d12` |
| 에러 텍스트 | Typography/red500 | Red/500 | `#fc3b3b` |

### 주요 컬러
| 용도 | Hex |
|------|-----|
| JK Brand Primary | `#1b55f6` (JKblue/500) |
| AM Brand Primary | `#ff6d12` (AMorange/500) |
| Error | `#fc3b3b` (Red/500) |
| Success | `#0dbc7c` (Green/500) |
| Warning | `#f0b500` (Yellow/500) |
| Info | `#207cf4` (Blue/600) |
| Background (Light) | `#ffffff` |
| Background (Dark) | `#1a1a1e` |

### Radius (테마별)
| 사이즈 | JK | AM |
|--------|----|----|
| xl2 | 16px | 20px |
| xl | 12px | 18px |
| lg | 10px | 16px |
| md | 10px | 16px |
| sm | 10px | 12px |

## 상충 해소 기준

JAMS 2.1 파일에서 같은 개념이 여러 이름으로 존재하는 경우, 아래 기준으로 하나를 선택합니다.

**Radius** — 파운데이션 레벨에서 10단계 정규 세트(0, 2, 4, 6, 8, 12, 16, 20, 24, 999)를 기준으로 삼고, 테마별 Radius(xl2~sm)는 컴포넌트 적용값으로 사용합니다.

**Shadow** — 각 shadow 토큰(default, list, white, button 등)은 용도별로 구분된 별개의 토큰입니다. 이름이 겹치는 경우 구체적인 수치(x, y, blur)가 정의된 쪽을 우선합니다.

**Subway 컬러** — Primitive의 `Color/Subway/line*`이 hex 원본이며, Component의 `Subway/bg/line*`은 이를 참조하는 alias입니다. hex값은 Primitive 기준으로 제공합니다.

## 응답 규칙

### 1. 레퍼런스에서 정확한 값을 찾아 제공
토큰 값을 추측하지 말고, `references/` 파일을 읽어서 실제 값을 참조하세요.

### 2. 코드로 바로 쓸 수 있게 변환
출력 형식 우선순위: **Tailwind config > CSS 변수 > TypeScript 상수** (별도 지정 없을 때)

### 3. 시맨틱 매핑도 함께 안내
Primitive 값(hex)과 함께 시맨틱 토큰이 Light/Dark에서 어떤 값을 갖는지 매핑도 제공하세요.

### 4. 컴포넌트 코딩 시 토큰 자동 적용
"JAMS 스타일로 버튼 만들어줘" 같은 요청에는 이 스킬의 토큰을 적용해 바로 코드를 생성하세요.

### 5. 전체 덤프 요청 시 레퍼런스를 코드 형식으로 완전 변환
"전체 컬러 Tailwind config로 줘" 요청이 오면, 레퍼런스 전체를 읽어서 요청한 코드 형식으로 변환하세요.
