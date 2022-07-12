state의 타입을 설정하던 중 type과 interface 2가지가 있어 조사를 해봤다.

# Type & Interface

type과 interface는 객체의 타입의 이름을 지정하는 방법이다.

```typescript
///interface
interface interface_Type {
  name: string;
  age: number;
}

///type
type type_Type = {
  name: string;
  age: number;
};
```

# 차이점

## 선언적 확장

interface로 선언한 타입을 확장하는 방법으로 동일한 이름으로 타입을 선언 시 타입이 확장되는 방법으로 type으로 선언된 타입은 동일한 이름으로 선언 시 오류가 발생한다.

### interface

```typescript
interface Window {
  name: string;
}
//동일한 이름으로 선언
interface Window {
  age: number;
}
/*동일한 이름으로 선언 시 자동으로 확장
interface Window {
  name:string
  age:number
}*/
```

### type

```typescript
const src = 'const a = "Hello World"';
window.ts.transpileModule(src, {});

type Window = {
  title: string;
};

type Window = {
  ts: TypeScriptAPI;
};

// Error: Duplicate identifier 'Window'.
```

## tuple, intersection, union

interface에서는 tuple, intersection, union 타입을 사용하지 못한다.

# 어떤걸 사용할까?

서로 비슷한 타입 선언 방식 중 어떤 방식을 사용해야할까? TypeScript 공식문서 내에서는 interface를 사용하는 것을 권하고 있으므로 이에 따르지만 union, tuple, Intersection을 사용해야 할 경우만 type를 사용하는 것을 추천한다.

<strong>For the most part, you can choose based on personal preference, and TypeScript will tell you if it needs something to be the other kind of declaration. If you would like a heuristic, use interface until you need to use features from type.</strong>
