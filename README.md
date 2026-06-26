# CSS Scroll Odyssey

JavaScript 없이 CSS scroll-driven animation으로 만드는 인터랙티브 스토리 실험입니다. sticky layout, scroll snap, view timeline, mask, blend mode를 조합해 스크롤 기반 장면 전환을 구현합니다.

## 목적
- 스크롤 기반 모션을 CSS만으로 실험한다.
- `CSS progressive enhancement` 원칙으로 scroll-driven animation을 기능 향상으로 다룬다.
- scroll-driven animation 미지원 브라우저에서도 읽을 수 있는 fallback을 유지한다.
- 중앙 maintainer bot이 새 장면, 접근성, fallback, 문서 개선을 target profile 기반 PR로 제안한다.

## 사용자 flow
1. 페이지를 스크롤하며 장면 전환을 본다.
2. 각 장면의 카드가 viewport 진입률에 따라 드러나는지 확인한다.
3. 후속 PR에서 새 장면과 fallback을 확장한다.

## 실행 방법
```bash
pnpm install
pnpm dev
```

## 검증
```bash
pnpm check
```

`pnpm check`는 `pnpm lint`, `pnpm build`, `pnpm no-js:dist`를 순서대로 실행해 source와 build output 모두에서 런타임 JavaScript가 없는지 검사한다.

## Vercel 배포
- 배포 설정: `vercel.json`
- framework: Vite
- build command: `pnpm build`
- output directory: `dist`
- production deploy: Vercel CLI 로그인 또는 `VERCEL_TOKEN` 설정 후 `npx vercel --prod --yes`

현재 저장소는 Vercel 정적 배포 설정까지 준비되어 있다. 이 Codex 실행 환경에서는 Vercel CLI/커넥터 인증이 확인되지 않아 production URL 발급은 인증 후 진행한다.

## 최근 업데이트
- 밝은 톤 스크롤 오디세이 디자인 시스템과 scroll-snap 장면 표현을 정리했다.
- CSS-only 스크롤 챕터, 진행감, fallback 설명을 작은 PR 단위로 개선했다.
- 중앙 maintainer bot은 스크롤 장면 전환 맥락과 최근 PR 이력을 기준으로 독립적인 개선 후보를 찾는다.

## 자가 개선
이 저장소에는 자가 개선 엔진을 두지 않는다. 중앙 control plane인 `okorion/self-improving-maintainer-bot`이 `profiles/overtura/css-scroll-odyssey.json` profile로 이 저장소를 target repo로 다룬다.

Target 설정은 `maintainer-bot/`에 둔다. 런타임 JavaScript, `.github/workflows/**`, credential, auth/security, infra, migration 변경은 R3로 취급하며 draft/proposal only로 처리한다.

## 디자인 시스템
- 기준 문서: `DESIGN.md`
- 실행 토큰: `design-system/base.css`
- 참고 기록: `docs/design/`

## 범위 밖
- 런타임 JavaScript
- SPA router
- 실제 secret 또는 credential 저장
