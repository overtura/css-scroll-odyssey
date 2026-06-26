# AGENTS.md

## Project Goal
이 저장소는 JavaScript 없이 CSS scroll-driven animation으로 밝은 인터랙티브 스토리를 만드는 overtura 실험 저장소다. 중앙 maintainer bot은 작은 PR 단위로 장면, 접근성, fallback을 개선한다.

## Commands
- install: `pnpm install`
- dev: `pnpm dev`
- lint: `pnpm lint`
- build: `pnpm build`
- full check: `pnpm check`

## Done Definition
- 화면 문구는 기본적으로 한국어다.
- `index.html`과 build output에 런타임 `<script>`가 없다.
- scroll story가 JavaScript 없이 읽히고 동작한다.
- PR 요약에 검증 결과가 있다.

## Review Guidelines
- JavaScript scroll hijacking을 추가하지 않는다.
- no-JS 제약, text-obscuring animation, 깨진 mobile layout, 과한 workflow 권한을 우선 지적한다.
- 중앙 maintainer bot 변경은 target profile, deny path, no-JS 제약, `pnpm check` 통과 여부를 먼저 본다.

## Central Maintainer Bot Rules
- 자가 개선 엔진은 이 저장소에 두지 않고 `okorion/self-improving-maintainer-bot` 중앙 control plane에서 실행한다.
- 이 저장소에는 `maintainer-bot/project.json`, `maintainer-bot/backlog.md`, `maintainer-bot/evals/docs_qa.jsonl`만 target repo 설정으로 둔다.
- 반복 루프는 작은 PR 하나로 끝나야 하며, `maintainer-bot/backlog.md`의 후보를 우선 활용한다.
- `.github/workflows/**`, credential, auth/security, infra, migration 성격의 변경은 R3로 취급하고 draft/proposal only로 다룬다.
- 런타임 JavaScript, 실제 secret, API key는 추가하지 않는다.

## External Design Tool Rules
- UI 작업 전 `DESIGN.md`, `design-system/base.css`, no-JS 검증 규칙을 먼저 읽는다.
- `portfolio-design-tools-integration-pack`과 외부 디자인 레퍼런스는 참고 자료이며 source of truth가 아니다.
- 외부 브랜드의 정확한 로고, 폰트, 고유 composition을 복제하지 않는다.
- token 또는 shared component contract 변경은 별도 design-system 성격의 PR로 분리한다.
