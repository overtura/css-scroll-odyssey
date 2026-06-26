# DESIGN.md - CSS Scroll Odyssey

## Product Intent
JavaScript 없이 CSS scroll-driven animation으로 진행되는 한국어 인터랙티브 스토리다. 사용자는 스크롤만으로 장면 전환, sticky rhythm, fallback을 경험한다.

## Design Authority
우선순위는 접근성, no-JS 제약, 이 문서, CSS semantic token, 외부 디자인 참고 순서다.

## Visual Character
```txt
Cinematic
Readable
Scroll-native
Restrained
```

- 어두운 항해 배경과 warm celestial accent를 사용한다.
- 장면 카드는 문장과 상태를 읽는 중심 요소다.
- scroll animation은 hierarchy를 보여주기 위한 수단이지 content를 숨기는 장치가 아니다.
- 미지원 브라우저에서도 모든 장면이 읽혀야 한다.

## Typography
- UI: Inter, Pretendard, system-ui
- Display: 48-108px
- Scene title: 40-84px
- Body: 18/31

## Layout
- 각 chapter는 viewport 단위 section이다.
- Header는 fixed이지만 content를 가리지 않도록 충분한 section padding을 둔다.
- Scene card radius는 8px 이하, backdrop blur는 낮게 유지한다.

## Component Rules
- Scene card는 number, title, description을 포함한다.
- `animation-timeline`은 progressive enhancement로만 쓴다.
- No horizontal page scroll.

## Interaction Model
```txt
Scroll -> Reveal chapter -> Read scene -> Continue
```

## Anti-patterns
- JavaScript scroll hijacking
- text-obscuring animation
- giant decorative card stack
- brand-specific visual clone
