# c2kim-claude-plugin

c2kim's personal Claude Code plugin.
React / Next.js 개발 컨벤션과 학습용 튜터 모드를 스킬로 묶어둔 개인용 플러그인.

컨벤션은 계속 바뀔 여지가 있어 스킬 내용도 수시로 업데이트된다.

## Skills

| Skill | 언제 발동 |
|-------|-----------|
| `create-component` | React/Next.js 새 컴포넌트 생성 시 (라우터 페이지 제외) |
| `create-hook` | 새 custom-hook 생성 시 |
| `create-tanstack-query` | tanstack-query(v5) 쿼리/뮤테이션 작성 시 |
| `write-test-code` | tsx/jsx 컴포넌트 테스트 작성 시 (기본 스택: vitest + RTL) |
| `tutor` | "튜터처럼 알려줘" 등 명시적으로 튜터형 설명을 요청할 때 |

## 설치

Claude Code에서 로컬 플러그인으로 로드하거나, marketplace에 등록해 사용한다.
스킬은 `skills/` 디렉토리에서 자동 인식된다.
