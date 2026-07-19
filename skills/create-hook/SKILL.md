---
name: create-hook
description: react, nextjs 환경에서 새로운 custom-hook 생성시 사용됨. 사용자가 hook 구현해줘, 훅 만들어줘 등 구현 타겟이 custom-hook 일 경우에 사용
---

## Convention
- 모듈 컨벤션은 프로젝트를 따르지만 일관되지 않다면 `kebab-case`를 사용 `ex) use-custom-hook`
- props가 3개 이상일때는 `object`로 받을 것.
- props 타입은 프로젝트를 따르지만 일관되지 않다면 `type-alias`를 사용
- props 타입 네이밍은 프로젝트를 따르지만 일관되지 않다면 `pascal-case`를 사용 `ex) UseCustomHookProps`
- `useEffect` 내부에 이벤트 핸들러가 들어가고 핸들러 내부에서 trace되어야 하는 상태가 `useEffect` 내부에 의존성으로 들어갔다면 `useEffectEvent`를 적극 사용.
