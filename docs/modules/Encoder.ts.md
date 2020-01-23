---
title: Encoder.ts
nav_order: 4
parent: Modules
---

# Encoder overview

Added in v3.0.0

---

<h2 class="text-delta">Table of contents</h2>

- [Encoder (interface)](#encoder-interface)
- [URI (type alias)](#uri-type-alias)
- [URI (constant)](#uri-constant)
- [encoder (constant)](#encoder-constant)
- [id (constant)](#id-constant)
- [array (function)](#array-function)
- [intersection (function)](#intersection-function)
- [lazy (function)](#lazy-function)
- [partial (function)](#partial-function)
- [record (function)](#record-function)
- [tuple (function)](#tuple-function)
- [type (function)](#type-function)

---

# Encoder (interface)

**Signature**

```ts
export interface Encoder<A> {
  readonly encode: (a: A) => unknown
}
```

Added in v3.0.0

# URI (type alias)

**Signature**

```ts
export type URI = typeof URI
```

Added in v3.0.0

# URI (constant)

**Signature**

```ts
export const URI: "Encoder" = ...
```

Added in v3.0.0

# encoder (constant)

**Signature**

```ts
export const encoder: S.Schema<URI> = ...
```

Added in v3.0.0

# id (constant)

**Signature**

```ts
export const id: Encoder<unknown> = ...
```

Added in v3.0.0

# array (function)

**Signature**

```ts
export function array<A>(encoder: Encoder<A>): Encoder<Array<A>> { ... }
```

Added in v3.0.0

# intersection (function)

**Signature**

```ts
export function intersection<A, B, C, D, E>(
  encoders: [Encoder<A>, Encoder<B>, Encoder<C>, Encoder<D>, Encoder<E>]
): Encoder<A & B & C & D & E>
export function intersection<A, B, C, D>(
  encoders: [Encoder<A>, Encoder<B>, Encoder<C>, Encoder<D>]
): Encoder<A & B & C & D>
export function intersection<A, B, C>(encoders: [Encoder<A>, Encoder<B>, Encoder<C>]): Encoder<A & B & C>
export function intersection<A, B>(encoders: [Encoder<A>, Encoder<B>]): Encoder<A & B> { ... }
```

Added in v3.0.0

# lazy (function)

**Signature**

```ts
export function lazy<A>(f: () => Encoder<A>): Encoder<A> { ... }
```

Added in v3.0.0

# partial (function)

**Signature**

```ts
export function partial<A>(encoders: { [K in keyof A]: Encoder<A[K]> }): Encoder<Partial<A>> { ... }
```

Added in v3.0.0

# record (function)

**Signature**

```ts
export function record<A>(encoder: Encoder<A>): Encoder<Record<string, A>> { ... }
```

Added in v3.0.0

# tuple (function)

**Signature**

```ts
export function tuple<A extends [unknown, unknown, ...Array<unknown>]>(
  encoders: { [K in keyof A]: Encoder<A[K]> }
): Encoder<A> { ... }
```

Added in v3.0.0

# type (function)

**Signature**

```ts
export function type<A>(encoders: { [K in keyof A]: Encoder<A[K]> }): Encoder<A> { ... }
```

Added in v3.0.0