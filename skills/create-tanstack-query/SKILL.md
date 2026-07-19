---
name: create-tanstack-query
description: tanstack-query를 생성할때 사용됨. 명시적으로 tanstack-query를 사용해줘가 아니더라도 구현 대상이 tanstack-query 관련일때 사용됨.
---

> 기준 버전: `@tanstack/react-query` v5

## Convention
- `query-key`는 function으로 작성한다.
  ```ts
  const createKey = () => ["queryKey"];
  const createKeyById = (id: string) => ["queryKey", id];
  ```
- `useMutation`은 소비하는 컴포넌트에서 선언 후 사용한다. `onSuccess, onError` 콜백은 `useMutation` 선언 시점이 아니라, 만들어진 인스턴스를 실제로 실행하는 `mutate` 호출 시점에 넘긴다.

  **금지 케이스** — 선언 시점에 콜백을 넣는다
  ```ts
  const mutation = useMutation({
    mutationFn: fn,
    onSuccess: () => {},
    onError: () => {},
  });
  ```

  **허용 케이스** — 호출 시점(`mutate`의 두 번째 인자)에 콜백을 넘긴다
  ```ts
  const mutation = useMutation({ mutationFn: fn });

  const handleMutation = () => {
    mutation.mutate(variables, {
      onSuccess: () => {},
      onError: () => {},
    });
  };
  ```
  > 참고: 호출 시점 콜백은 컴포넌트가 언마운트되면 실행되지 않는다. 언마운트 후에도 반드시 실행돼야 하는 로직(캐시 invalidate 등)은 선언 시점 콜백에 둔다.
