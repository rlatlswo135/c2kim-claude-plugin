---
name: write-test-code
description: React로 작성된 컴포넌트의 컴포넌트 테스트 작성시 사용됨. 해당 모듈이 반드시 tsx, jsx로 작성된 경우에만 사용되어야 한다.
---

## Stack
- 테스트 스택은 프로젝트를 따르되, 명시된 것이 없다면 `vitest`(+ React Testing Library)를 사용.

## Rules
- a11y 관련 테스트는 명시적으로 요구했을때만 작성.
- Transition 관련 테스트는 명시적으로 요구했을때만 작성.
- 디자인 관련 테스트는 visibility on -> off 등 큰 변경사항에 대해서만 작성.
  - 단 그 디자인이 form 등 validation 관련 일때는 작성
- **컴포넌트 내부에 네트워크 호출이 있어도 모킹을 통한 테스트는 하지 않는다**
  - 컴포넌트가 가진 고유의 기능에 대해서만 테스트 가능해야함.
  - 엘리먼트 고유의 인터랙션 테스트 등은 진행하지 않음.
    - 단 disabled 같은 validation 관련 일때는 작성
