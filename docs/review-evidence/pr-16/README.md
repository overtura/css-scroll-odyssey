# PR #16 시각 검증 기록

## 대상

- 변경 전: `657a96e0e506f78884aa17e06116b1ff36a2e1e8`
- 변경 후(캡처 기준 head): `e774c9252b7ca3d1668c39d946aeb29cdc0322a0`
- 대상 요소: `#signal .chapter-copy`
- 검증 브라우저: Playwright Chromium (1440 × 1000, 560 × 1000)

`c7b558a`에서 CSS 13줄을 변경했고 `e774c92`에서 README 39줄과 PNG 4개를 추가했습니다. 이후 증빙 메타데이터 정정은 제품 CSS와 PNG를 바꾸지 않았으며, 전체 diff는 6개 파일, `+52/-0`입니다.

## 캡처

| 상태 | 데스크톱 1440 × 1000 | 모바일 560 × 1000 |
| --- | --- | --- |
| 변경 전 | [캡처](./before-signal-desktop-1440x1000.png) | [캡처](./before-signal-mobile-560x1000.png) |
| 변경 후 | [캡처](./after-signal-desktop-1440x1000.png) | [캡처](./after-signal-mobile-560x1000.png) |

각 캡처는 정적 서버에서 `index.html#signal`을 열고 `#signal .chapter-copy`가 표시된 뒤 1.2초 후 촬영했습니다.

## 레이아웃 검증

| 상태 | 뷰포트 | 문서 `clientWidth / scrollWidth` | 가로 overflow | 텍스트 잘림 | `chapter-copy` 경계 `(left, top, right, bottom)` | 런타임 script |
| --- | --- | --- | ---: | ---: | --- | ---: |
| 변경 전 | 1440 × 1000 | 1440 / 1440 | 0px | 0건 | `(72, 414, 502, 777)` | 0개 |
| 변경 후 | 1440 × 1000 | 1440 / 1440 | 0px | 0건 | `(72, 359, 502, 832)` | 0개 |
| 변경 전 | 560 × 1000 | 560 / 560 | 0px | 0건 | `(20, 292, 540, 639)` | 0개 |
| 변경 후 | 560 × 1000 | 560 / 560 | 0px | 0건 | `(20, 292, 540, 691)` | 0개 |

변경 후 카드의 좌우 경계는 두 뷰포트 모두 화면 안에 있고, 제목·본문·목록·링크에서 `overflow: hidden/clip`에 의한 잘림은 발견되지 않았습니다. 560px에서는 PR의 반응형 패딩 `24px 20px`이 적용됩니다.

## 파일 무결성

| 파일 | SHA-256 |
| --- | --- |
| `before-signal-desktop-1440x1000.png` | `530BF99C71170B9B1C138A38308940EA2DB7A84BD12727F9E57D7813B415CD75` |
| `after-signal-desktop-1440x1000.png` | `1BB652C86041D2D106E37537A7CB53B23BDACEFB9039E45455E3C82B014FE8CC` |
| `before-signal-mobile-560x1000.png` | `0C85BDCC3EF38B8ED9ADE05143CA672CF1DEF870113229A94A6B1C52151FCF3E` |
| `after-signal-mobile-560x1000.png` | `3285F034BF3B24F5498383758620CADD291BCEFBB56ACABD49FB0D61F5F78AB2` |
