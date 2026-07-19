---
name: create-react-component
description: react, nextjs 환경에서 새로운 컴포넌트 생성시 사용됨. 반드시 새로운 컴포넌트를 생성할때 사용되어야 함. 단 Next.js의 router내 페이지일경우엔 실행 안함. 반드시 '컴포넌트' 일것. 사용자가 컴포넌트 구현해줘, 컴포넌트 생성해줘 등 구현 타겟이 컴포넌트 일 경우에 사용
---

## Convention
1. 'export' 로 내보낼것. default export 금지
2. 컴포넌트 및 컴포넌트 내부 함수는 모두 `arrow-function` 으로 구현할것
3. `constant`는 같은 모듈내 컴포넌트 외부 컨텍스트에 작성할것 ex) `const TEST = ""; const NewComponent = () => {...};`
4. `onClick, onChange`등 이벤트 함수의 네이밍은 `handle-{name}`으로 작성할것. 단 해당내용만으론 부족할때 중간에 약간의 정보 삽입가능 ex) `handleClick / handleChange / handleNavClick`
5. 작성하는 컴포넌트가 props로 이벤트 핸들러를 받을때는 `{name}Handler`로 받을것. 단 같은 액션 이벤트 핸들러를 받아 도메인적 구분이 부족할땐 중간에 약간의 정보 삽입 가능 ) `clickHandler / changeHandler / changeNavHandler`
6. `react-compiler` 적용을 기준으로함. 즉 명시적으로 `useMemo / useCallback` 등 memoization 관련 기능은 사용금지.
7. 컴포넌트 내부는 `state`에 종속적이거나 `event-handler` 같은 컴포넌트 내부와 직접적인 관련이 있는 함수들만 존재한다, 로직 내 데이터 가공만을 위해 존재하는 함수 등 util성격이 강한 함수는 `constant`와 마찬가지로 모듈 외부로 작성할것.
8. 컴포넌트가 위치할 모듈의 이름은 프로젝트를 따르지만 기본은 `kebab-case`로 작성한다.
9. props 타입은 프로젝트를 따르지만 일관치 않다면 `type-alias`를 사용.
10. 타입추론이 가능한 경우에는 제네릭을 굳이 명시하지 않는다. 즉 다음과 같은 형태는 금지한다. ex) `const [val,setVal] = useState<number>(30) // number = 원시타입. ts에서 추론가능`
11. `Suspense` 및 `ErrorBoundary` 등을 적극 사용한다. promise 및 context 처리는 `use`를 적극 사용할 것.
