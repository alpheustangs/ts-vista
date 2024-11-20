[ts-vista](../README.md) / Exclude

# Type Alias: Exclude\<T, U\>

> **Exclude**\<`T`, `U`\>: `T` *extends* `U` ? `never` : `T`

Exclude from T those types that are assignable to U.

### Example

```ts
import type { Exclude } from "ts-vista";

type T1 = {
  type: "a";
  name: string;
};

type T2 = {
  type: "b";
  age: number;
};

type T3 = {
  type: "c";
  color: string;
};

type T4 = T1 | T2 | T3;

// D1X = T2 | T3
type D1A = Exclude<T4, T1>;
type D1B = Exclude<T4, { type: "a"; name: string }>;

// D2X = T3
type D2A = Exclude<T4, T1 | T2>;
type D2B = Exclude<
    T4,
    | { type: "a"; name: string }
    | { type: "b"; age: number }
>;
```

## Type Parameters

• **T**

• **U** *extends* `T`

## Defined in

[@types/exclude.ts:39](https://github.com/alpheustangs/ts-vista/blob/c55ddd747aa287607cf84dd6de142b1ed1e2f70a/package/src/@types/exclude.ts#L39)