# CSS Scroll Odyssey Maintainer Bot Backlog

중앙 control plane은 `okorion/self-improving-maintainer-bot`이다. 스크롤 hijacking 없이 CSS progressive enhancement를 유지한다.

## 운영 검증
- 모든 변경은 `pnpm check`를 통과해야 한다.
- 자동 merge 기본값은 꺼져 있다.
- `.github/workflows/**`, credential, auth/security, infra, migration 변경은 R3로 취급하고 코드 변경 없이 proposal only로 다룬다.

## R0 Report
- scroll-driven animation과 fallback의 역할을 분석 리포트로 정리한다.
- 장면 추가 시 지켜야 할 section 구조와 heading 규칙을 정리한다.

## R1 PR 후보
- HTML/CSS만 사용하는 새 chapter 후보를 작게 추가한다.
- 기존 chapter 설명을 더 구체적인 한국어로 보강한다.
- 밝은 하늘색 기반 배경을 유지하면서 scene card 가독성을 개선한다.

## R2 Draft 후보
- build tooling, dependency, lint script 변경은 draft PR로만 제안한다.

## R3 Proposal only
- workflow, credential, security, infra, migration 관련 변경은 코드 변경 없이 proposal로만 다룬다.
