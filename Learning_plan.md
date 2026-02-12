# TypeScript Learning Plan (By Stages)

> **Tip:** Mark each task as completed by replacing 🚧 with ✅.
> **Updated:** February 2026 — covers TypeScript 5.x

---

## Stage 1 — Introduction & Environment Setup 🚧
- What is TypeScript 🚧
  - [ ] TypeScript as a typed superset of JavaScript
  - [ ] Why TypeScript: catching errors at compile time, better tooling, self-documenting code
  - [ ] TypeScript vs JavaScript — what TS adds, what it does not change
  - [ ] How TypeScript compiles to JavaScript (erasure-based type system)
  - [ ] TypeScript versioning and release cadence
- Installing and configuring TypeScript 🚧
  - [ ] Installing TypeScript globally (`npm install -g typescript`)
  - [ ] Installing locally per project (`npm install --save-dev typescript`)
  - [ ] The `tsc` compiler — compiling `.ts` files
  - [ ] `tsc --init` — generating `tsconfig.json`
  - [ ] Key `tsconfig.json` options: `target`, `module`, `strict`, `outDir`, `rootDir`, `sourceMap`
  - [ ] `include`, `exclude`, and `files` in `tsconfig.json`
  - [ ] Strict mode flags: `strictNullChecks`, `noImplicitAny`, `strictFunctionTypes`, etc.
  - [ ] Watch mode (`tsc --watch`)
- TypeScript tooling 🚧
  - [ ] VS Code TypeScript support (built-in IntelliSense, error highlighting)
  - [ ] TypeScript Playground (online experimentation)
  - [ ] `ts-node` — running TypeScript directly without pre-compiling
  - [ ] `tsx` — fast TypeScript execution for Node.js
  - [ ] ESLint with TypeScript (`@typescript-eslint/parser`, `@typescript-eslint/eslint-plugin`)
  - [ ] Prettier with TypeScript
- Project structure conventions 🚧
  - [ ] Typical TypeScript project layout (`src/`, `dist/`, `tsconfig.json`)
  - [ ] `package.json` scripts for TypeScript (`build`, `dev`, `typecheck`)
  - [ ] Source maps and debugging TypeScript
- Mini-project: Set up a TypeScript project from scratch 🚧
  - Initialize a Node.js project, install TypeScript, configure `tsconfig.json`, write a simple program, compile and run it

**Useful Resources:**
- [TypeScript Official Handbook — Get Started](https://www.typescriptlang.org/docs/handbook/typescript-from-scratch.html)
- [TypeScript Download & Installation](https://www.typescriptlang.org/download)
- [TSConfig Reference](https://www.typescriptlang.org/tsconfig)
- [TypeScript Playground](https://www.typescriptlang.org/play)
- [ts-node](https://typestrong.org/ts-node/)
- [tsx](https://tsx.is/)

---

## Stage 2 — Basic Types & Type Annotations 🚧
- Type annotations and type inference 🚧
  - [ ] Explicit type annotations (`: type` syntax)
  - [ ] Type inference — when TypeScript infers types automatically
  - [ ] When to annotate vs when to rely on inference
  - [ ] The balance: annotate function signatures, let inference handle locals
- Primitive types 🚧
  - [ ] `string`, `number`, `boolean`
  - [ ] `null` and `undefined` as types
  - [ ] `bigint` and `symbol` types
- Special types 🚧
  - [ ] `any` — opting out of type checking (and why to avoid it)
  - [ ] `unknown` — the type-safe counterpart of `any`
  - [ ] `void` — for functions that do not return a value
  - [ ] `never` — for functions that never return (throw or infinite loop)
  - [ ] `undefined` vs `void` in return types
- Arrays and tuples 🚧
  - [ ] Array types (`number[]` vs `Array<number>`)
  - [ ] Readonly arrays (`readonly number[]`, `ReadonlyArray<number>`)
  - [ ] Tuples — fixed-length, fixed-type arrays (`[string, number]`)
  - [ ] Optional tuple elements (`[string, number?]`)
  - [ ] Rest elements in tuples (`[string, ...number[]]`)
  - [ ] Named tuple elements (`[name: string, age: number]`) (TS 4.0+)
- Object types 🚧
  - [ ] Inline object type annotations (`{ name: string; age: number }`)
  - [ ] Optional properties (`?`)
  - [ ] Readonly properties (`readonly`)
  - [ ] Index signatures (`[key: string]: unknown`)
- Literal types 🚧
  - [ ] String literal types (`"hello"`)
  - [ ] Numeric literal types (`42`)
  - [ ] Boolean literal types (`true`, `false`)
  - [ ] `as const` assertions — widening vs narrowing
  - [ ] `const` type parameters (TS 5.0+)
- Type assertions 🚧
  - [ ] `as` syntax (`value as Type`)
  - [ ] Angle bracket syntax (`<Type>value`) — and why `as` is preferred
  - [ ] Non-null assertion operator (`!`)
  - [ ] `satisfies` operator (TS 4.9+) — validate type without widening
  - [ ] When to use assertions vs type guards
- Mini-project: Type-safe configuration loader 🚧
  - Build a module that reads configuration from an object, validates types at compile time, provides typed access with defaults and required fields

**Useful Resources:**
- [TypeScript Handbook — Everyday Types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html)
- [TypeScript Handbook — Type Inference](https://www.typescriptlang.org/docs/handbook/type-inference.html)
- [TypeScript Handbook — Type Assertions](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#type-assertions)
- [TypeScript 4.9 — `satisfies` Operator](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-4-9.html)
- [TypeScript 5.0 — `const` Type Parameters](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-5-0.html)

---

## Stage 3 — Interfaces & Type Aliases 🚧
- Interfaces 🚧
  - [ ] Declaring interfaces (`interface Name { ... }`)
  - [ ] Optional properties (`property?: type`)
  - [ ] Readonly properties (`readonly property: type`)
  - [ ] Method signatures in interfaces
  - [ ] Call signatures and construct signatures
  - [ ] Extending interfaces (`extends`) — single and multiple
  - [ ] Declaration merging — adding properties to existing interfaces
  - [ ] Interfaces for function types
- Type aliases 🚧
  - [ ] Declaring type aliases (`type Name = ...`)
  - [ ] Type aliases for primitives, unions, tuples, objects
  - [ ] Type aliases for function types
  - [ ] Generic type aliases (introduction)
- Interface vs Type alias 🚧
  - [ ] When to use `interface` (object shapes, extensibility, declaration merging)
  - [ ] When to use `type` (unions, intersections, mapped types, complex compositions)
  - [ ] Performance considerations (interfaces are generally faster for the compiler)
  - [ ] Team conventions and consistency
- Intersection types 🚧
  - [ ] Combining types with `&`
  - [ ] Merging object types
  - [ ] Intersection with interfaces
  - [ ] Intersection conflicts (same property with different types)
- Index signatures and record patterns 🚧
  - [ ] String index signatures (`[key: string]: type`)
  - [ ] Number index signatures (`[index: number]: type`)
  - [ ] Combining known and dynamic properties
  - [ ] `Record<Keys, Type>` as an alternative to index signatures
- Mini-project: Data models for an e-commerce system 🚧
  - Define interfaces and types for a product catalog: `Product`, `Category`, `CartItem`, `Order`, `User`, `Address` — using extends, optional properties, readonly, and intersection types

**Useful Resources:**
- [TypeScript Handbook — Object Types](https://www.typescriptlang.org/docs/handbook/2/objects.html)
- [TypeScript Handbook — Interfaces](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#interfaces)
- [TypeScript Handbook — Type Aliases](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#type-aliases)
- [TypeScript Handbook — Intersection Types](https://www.typescriptlang.org/docs/handbook/2/objects.html#intersection-types)
- [Interface vs Type in TypeScript (Matt Pocock)](https://www.totaltypescript.com/type-vs-interface-which-should-you-use)

---

## Stage 4 — Union Types, Enums & Type Narrowing 🚧
- Union types 🚧
  - [ ] Declaring union types (`type A = string | number`)
  - [ ] Working with union types — accessing common properties only
  - [ ] Union types in function parameters
  - [ ] Literal union types as enumerations (`type Direction = "up" | "down" | "left" | "right"`)
  - [ ] Discriminated unions (tagged unions) — objects with a common literal property
  - [ ] Type-safe state machines with discriminated unions (State, Event, reducer pattern)
  - [ ] Exhaustive checking with `never`
- Type narrowing 🚧
  - [ ] `typeof` guards (`typeof x === "string"`)
  - [ ] Truthiness narrowing (`if (x)`)
  - [ ] Equality narrowing (`===`, `!==`, `==`, `!=`)
  - [ ] `instanceof` narrowing
  - [ ] `in` operator narrowing (`"property" in obj`)
  - [ ] Assignment narrowing
  - [ ] Control flow analysis — how TypeScript tracks types through code
- Type guards and type predicates 🚧
  - [ ] User-defined type guards (`function isType(val): val is Type`)
  - [ ] Assertion functions (`function assert(val): asserts val is Type`)
  - [ ] Combining type guards with discriminated unions
  - [ ] Generic type guards
- Enums 🚧
  - [ ] Numeric enums (auto-incrementing, custom values)
  - [ ] String enums
  - [ ] Heterogeneous enums (mixed — generally avoid)
  - [ ] `const enum` — inlined at compile time
  - [ ] Reverse mapping in numeric enums
  - [ ] Enums vs union literal types — trade-offs
  - [ ] When enums are appropriate vs when unions are better
- The `satisfies` operator in practice 🚧
  - [ ] Validating a value matches a type without widening
  - [ ] `satisfies` with `as const` for precise literal inference
  - [ ] Common patterns: config objects, route definitions, color palettes
- Mini-project: Command-line argument parser 🚧
  - Build a type-safe CLI argument parser that uses discriminated unions for argument types (string, number, boolean, array), type guards for validation, and union types for option definitions

**Useful Resources:**
- [TypeScript Handbook — Narrowing](https://www.typescriptlang.org/docs/handbook/2/narrowing.html)
- [TypeScript Handbook — Unions and Intersection Types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#union-types)
- [TypeScript Handbook — Enums](https://www.typescriptlang.org/docs/handbook/enums.html)
- [TypeScript Handbook — Type Guards](https://www.typescriptlang.org/docs/handbook/2/narrowing.html#using-type-predicates)
- [Matt Pocock — Discriminated Unions](https://www.totaltypescript.com/discriminated-unions-are-a-best-practice)

---

## Stage 5 — Functions with TypeScript 🚧
- Function type annotations 🚧
  - [ ] Parameter type annotations
  - [ ] Return type annotations (explicit vs inferred)
  - [ ] Optional parameters (`param?: type`)
  - [ ] Default parameters with types
  - [ ] Rest parameters with types (`...args: number[]`)
- Function type expressions 🚧
  - [ ] Function type syntax (`(a: string, b: number) => boolean`)
  - [ ] Type aliases for function types
  - [ ] Interfaces with call signatures
  - [ ] `void` return type — permissive behavior (contextual typing)
- Function overloads 🚧
  - [ ] Overload signatures and implementation signature
  - [ ] When to use function overloads vs union types
  - [ ] Overloads with different return types based on input
  - [ ] Best practices: prefer unions, use overloads for complex cases
- The `this` parameter 🚧
  - [ ] Typing `this` in function declarations (`this: Type`)
  - [ ] `ThisParameterType<T>` utility type
  - [ ] `OmitThisParameter<T>` utility type
  - [ ] `this` in class methods
- Callback and higher-order function types 🚧
  - [ ] Typing callback parameters
  - [ ] Typing higher-order functions (functions returning functions)
  - [ ] Generic callbacks (introduction)
  - [ ] `Parameters<T>` and `ReturnType<T>` utility types
- `noUncheckedIndexedAccess` 🚧
  - [ ] Why indexed access returns `T | undefined` with this flag
  - [ ] Writing safer array and object access patterns
- Mini-project: Type-safe event emitter 🚧
  - Implement an `EventEmitter` class where event names and their payload types are defined via a type parameter; methods `on`, `off`, `emit` must enforce correct payload types per event name

**Useful Resources:**
- [TypeScript Handbook — More on Functions](https://www.typescriptlang.org/docs/handbook/2/functions.html)
- [TypeScript Handbook — Function Overloads](https://www.typescriptlang.org/docs/handbook/2/functions.html#function-overloads)
- [TypeScript Handbook — `this` Types](https://www.typescriptlang.org/docs/handbook/2/functions.html#declaring-this-in-a-function)
- [Matt Pocock — Function Overloads vs Unions](https://www.totaltypescript.com/typescript-function-overloads)

---

## Stage 6 — Generics 🚧
- Generic functions 🚧
  - [ ] Generic type parameters (`function identity<T>(arg: T): T`)
  - [ ] Type argument inference vs explicit type arguments
  - [ ] Multiple type parameters (`<T, U>`)
  - [ ] When to use generics vs `unknown` vs `any`
- Generic constraints 🚧
  - [ ] `extends` keyword for constraining generics (`<T extends HasLength>`)
  - [ ] Using `keyof` with generics (`<T, K extends keyof T>`)
  - [ ] Multiple constraints using intersection (`<T extends A & B>`)
  - [ ] Generic constraints with conditional logic
- Generic interfaces and type aliases 🚧
  - [ ] Generic interfaces (`interface Box<T> { value: T }`)
  - [ ] Generic type aliases (`type Pair<T, U> = [T, U]`)
  - [ ] Default type parameters (`<T = string>`)
  - [ ] `const` type parameters (TS 5.0+) — preventing widening of inferred literal types
- Generic classes 🚧
  - [ ] Class-level type parameters
  - [ ] Static members and generics (static members cannot reference class type parameters)
  - [ ] Generic class constraints
- `keyof` and indexed access types 🚧
  - [ ] `keyof T` — getting a union of property keys
  - [ ] Indexed access types (`T[K]`, `T["property"]`)
  - [ ] Using `keyof` and indexed access together in generic functions
  - [ ] `typeof` type operator — extracting type from a value
- Practical generic patterns 🚧
  - [ ] Generic wrapper / container types (`Result<T, E>`, `Option<T>`)
  - [ ] Type-safe pick and omit helper functions
  - [ ] Generic factory functions
  - [ ] Method chaining with generics (builder pattern)
  - [ ] Builder pattern with compile-time required field validation (`IsComplete<T, S>`)
- Mini-project: Generic data structures library 🚧
  - Implement type-safe `Stack<T>`, `Queue<T>`, and `LinkedList<T>` with full generic typing, constraints where needed, and iterator support (`Symbol.iterator`)

**Useful Resources:**
- [TypeScript Handbook — Generics](https://www.typescriptlang.org/docs/handbook/2/generics.html)
- [TypeScript Handbook — `keyof` Type Operator](https://www.typescriptlang.org/docs/handbook/2/keyof-types.html)
- [TypeScript Handbook — Indexed Access Types](https://www.typescriptlang.org/docs/handbook/2/indexed-access-types.html)
- [TypeScript Handbook — `typeof` Type Operator](https://www.typescriptlang.org/docs/handbook/2/typeof-types.html)
- [TypeScript 5.0 — `const` Type Parameters](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-5-0.html#const-type-parameters)

---

## Stage 7 — Classes with TypeScript 🚧
- Access modifiers 🚧
  - [ ] `public` (default)
  - [ ] `private` — accessible only within the class
  - [ ] `protected` — accessible within class and subclasses
  - [ ] `private` vs JavaScript `#` private fields — differences
  - [ ] When to use TS `private` vs JS `#private`
- Readonly and parameter properties 🚧
  - [ ] `readonly` modifier on class properties
  - [ ] Constructor parameter properties (`constructor(public name: string)`)
  - [ ] Combining modifiers (`private readonly`)
- Abstract classes 🚧
  - [ ] `abstract` class declaration
  - [ ] Abstract methods (must be implemented by subclasses)
  - [ ] Abstract properties
  - [ ] Abstract classes vs interfaces — when each is appropriate
- Implementing interfaces 🚧
  - [ ] `implements` keyword
  - [ ] Implementing multiple interfaces
  - [ ] Structural typing — classes are compatible if shapes match
  - [ ] `implements` does not change the class type
- Generics in classes 🚧
  - [ ] Generic class declarations
  - [ ] Constraining class type parameters
  - [ ] Generic methods within classes
- Advanced class patterns 🚧
  - [ ] `this` type in classes (fluent interfaces, method chaining)
  - [ ] Class expressions
  - [ ] Mixins pattern (TypeScript-specific implementation)
  - [ ] `InstanceType<T>` utility type
  - [ ] `ConstructorParameters<T>` utility type
  - [ ] `override` keyword (TS 4.3+) — explicit override of base class methods
  - [ ] Class `static` blocks (ES2022, TS 4.4+)
- Mini-project: Plugin system with abstract classes 🚧
  - Design a plugin architecture: an abstract `Plugin` base class with lifecycle hooks, a `PluginManager` that registers and manages plugins, concrete plugin implementations, all with strict typing via `implements` and generics

**Useful Resources:**
- [TypeScript Handbook — Classes](https://www.typescriptlang.org/docs/handbook/2/classes.html)
- [TypeScript Handbook — Abstract Classes](https://www.typescriptlang.org/docs/handbook/2/classes.html#abstract-classes-and-members)
- [TypeScript Handbook — Mixins](https://www.typescriptlang.org/docs/handbook/mixins.html)
- [TypeScript 4.3 — `override`](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-4-3.html#override-and-the---noimplicitoverride-flag)

---

## Stage 8 — Advanced Types 🚧
- Mapped types 🚧
  - [ ] Basic mapped types (`{ [K in keyof T]: ... }`)
  - [ ] Modifiers: adding/removing `readonly` and `?` (`+readonly`, `-?`)
  - [ ] Key remapping via `as` (`[K in keyof T as NewKey]: ...`) (TS 4.1+)
  - [ ] Filtering keys in mapped types (remapping to `never`)
  - [ ] Mapping over union types
- Conditional types 🚧
  - [ ] Basic conditional types (`T extends U ? X : Y`)
  - [ ] Distributive conditional types (how unions distribute)
  - [ ] Preventing distribution with `[T] extends [U]`
  - [ ] `infer` keyword — extracting types within conditional types
  - [ ] Nested conditional types
  - [ ] Practical patterns: `Flatten<T>`, `Awaited<T>`, `UnwrapPromise<T>`
- Template literal types 🚧
  - [ ] Basic template literal types (`` `hello-${string}` ``)
  - [ ] Combining with union types for string permutations
  - [ ] Intrinsic string manipulation types: `Uppercase`, `Lowercase`, `Capitalize`, `Uncapitalize`
  - [ ] Using template literals in mapped type key remapping
  - [ ] Practical patterns: event handler names, CSS property types, path patterns
- Built-in utility types — mastery 🚧
  - [ ] `Partial<T>`, `Required<T>`, `Readonly<T>`
  - [ ] `Pick<T, K>`, `Omit<T, K>`
  - [ ] `Record<K, T>`
  - [ ] `Exclude<T, U>`, `Extract<T, U>`
  - [ ] `NonNullable<T>`
  - [ ] `Parameters<T>`, `ConstructorParameters<T>`
  - [ ] `ReturnType<T>`, `InstanceType<T>`
  - [ ] `Awaited<T>` (TS 4.5+)
  - [ ] `NoInfer<T>` (TS 5.4+)
  - [ ] Implementing utility types from scratch for deep understanding
- Recursive types 🚧
  - [ ] Recursive type aliases (`type Nested<T> = T | Nested<T>[]`)
  - [ ] `DeepPartial<T>`, `DeepReadonly<T>`, `DeepRequired<T>`
  - [ ] JSON type definition (recursive)
  - [ ] Recursion depth limits and performance
- Variadic tuple types 🚧
  - [ ] Spread in tuple types (`[...T, ...U]`) (TS 4.0+)
  - [ ] Generic rest elements
  - [ ] Typing functions like `concat`, `curry`, `pipe` with variadic tuples
- Modern TypeScript type features 🚧
  - [ ] `satisfies` operator — deep patterns (TS 4.9+)
  - [ ] `const` type parameters (TS 5.0+)
  - [ ] `NoInfer<T>` utility type (TS 5.4+)
  - [ ] `${infer ...}` pattern matching in template literals
- Type testing patterns 🚧
  - [ ] `AssertEqual<T, U>` — testing type equality at compile time
  - [ ] `ExpectError<T>` — verifying that types produce errors
  - [ ] Writing inline type tests alongside code
  - [ ] When to use inline tests vs `tsd`/`expect-type`
- Real-world type patterns 🚧
  - [ ] Type-safe API client pattern (`ExtractParams`, `ExtractBody`, `ExtractResponse` with conditional types)
  - [ ] Type-safe form validation (`ValidationRule<T[K]>`, `ValidationErrors<T>`, `FormValidator<T>`)
- Mini-project: Type-safe ORM query builder 🚧
  - Build a query builder where table schemas are defined as types; methods like `select`, `where`, `orderBy`, and `join` use mapped types, conditional types, and template literals to ensure only valid column names and types are used at compile time

**Useful Resources:**
- [TypeScript Handbook — Mapped Types](https://www.typescriptlang.org/docs/handbook/2/mapped-types.html)
- [TypeScript Handbook — Conditional Types](https://www.typescriptlang.org/docs/handbook/2/conditional-types.html)
- [TypeScript Handbook — Template Literal Types](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html)
- [TypeScript Handbook — Utility Types](https://www.typescriptlang.org/docs/handbook/utility-types.html)
- [Type Challenges (GitHub)](https://github.com/type-challenges/type-challenges)
- [Matt Pocock — Total TypeScript (tutorials)](https://www.totaltypescript.com/)

---

## Stage 9 — Modules, Namespaces & Declaration Files 🚧
- ES Modules with TypeScript 🚧
  - [ ] `import` and `export` with type annotations
  - [ ] Type-only imports and exports (`import type { ... }`, `export type { ... }`) (TS 3.8+)
  - [ ] Inline type-only imports (`import { type Foo, bar }`) (TS 4.5+)
  - [ ] `verbatimModuleSyntax` tsconfig option (TS 5.0+) — enforcing explicit type-only imports
  - [ ] Module resolution strategies (`node`, `node16`, `nodenext`, `bundler`)
  - [ ] `moduleResolution: "bundler"` (TS 5.0+)
  - [ ] Path mapping and `baseUrl` in `tsconfig.json`
  - [ ] Barrel files (`index.ts`) — patterns and anti-patterns
- Namespaces (legacy) 🚧
  - [ ] `namespace` keyword — what it compiles to
  - [ ] When namespaces were used (pre-ES modules)
  - [ ] Why not to use namespaces in modern TypeScript
  - [ ] Namespaces vs modules — clear distinction
- Declaration files (`.d.ts`) 🚧
  - [ ] What declaration files are and why they exist
  - [ ] Generating `.d.ts` files from TypeScript (`declaration: true` in tsconfig)
  - [ ] Anatomy of a `.d.ts` file
  - [ ] `declare` keyword — ambient declarations
  - [ ] `declare module` — declaring module types
  - [ ] `declare global` — augmenting global scope
  - [ ] `declare const`, `declare function`, `declare class`
- DefinitelyTyped and `@types` 🚧
  - [ ] What DefinitelyTyped is
  - [ ] Installing type definitions (`npm install --save-dev @types/package`)
  - [ ] How `@types` resolution works (`typeRoots`, `types` in tsconfig)
  - [ ] Writing custom type definitions for untyped libraries
  - [ ] Contributing to DefinitelyTyped
- Module augmentation 🚧
  - [ ] Augmenting existing modules (`declare module "existing-module"`)
  - [ ] Interface merging across modules
  - [ ] Global augmentation (`declare global`)
  - [ ] Practical example: augmenting Express `Request` type
- Mini-project: Create and publish a typed utility library 🚧
  - Build a utility library (string helpers, array helpers, type guards), generate `.d.ts` declaration files, configure `package.json` for TypeScript consumers (`types` field), and write a type definition file for an imaginary untyped dependency

**Useful Resources:**
- [TypeScript Handbook — Modules](https://www.typescriptlang.org/docs/handbook/2/modules.html)
- [TypeScript Handbook — Declaration Files](https://www.typescriptlang.org/docs/handbook/declaration-files/introduction.html)
- [TypeScript Handbook — Module Resolution](https://www.typescriptlang.org/docs/handbook/modules/theory.html)
- [DefinitelyTyped (GitHub)](https://github.com/DefinitelyTyped/DefinitelyTyped)
- [TypeScript 5.0 — `verbatimModuleSyntax`](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-5-0.html#--verbatimmodulesyntax)

---

## Stage 10 — Decorators & Metadata 🚧
- Decorators overview 🚧
  - [ ] What decorators are — metaprogramming for classes
  - [ ] Use cases: logging, validation, dependency injection, serialization
  - [ ] History: experimental decorators (TS `--experimentalDecorators`) vs TC39 Stage 3 decorators (TS 5.0+)
  - [ ] Which to use: TC39 decorators for new projects, experimental for legacy/Angular
- TC39 Stage 3 decorators (TS 5.0+) 🚧
  - [ ] Decorator syntax (`@decorator`)
  - [ ] Class decorators — receiving the class constructor, returning a replacement or `void`
  - [ ] Class method decorators — `context.kind === "method"`, wrapping methods
  - [ ] Class getter/setter decorators
  - [ ] Class field decorators — initializer functions
  - [ ] Class auto-accessor decorators (`accessor` keyword)
  - [ ] Decorator context object (`DecoratorContext`)
  - [ ] Decorator metadata (`Symbol.metadata`) (TS 5.2+)
  - [ ] Decorator factories — decorators that accept arguments
  - [ ] Combining multiple decorators (composition order)
- Legacy experimental decorators 🚧
  - [ ] Enabling: `experimentalDecorators: true`, `emitDecoratorMetadata: true`
  - [ ] Class decorators
  - [ ] Method decorators (`target`, `propertyKey`, `descriptor`)
  - [ ] Property decorators
  - [ ] Parameter decorators
  - [ ] `reflect-metadata` library
  - [ ] Differences from TC39 decorators
- Practical decorator patterns 🚧
  - [ ] `@log` — method logging decorator
  - [ ] `@validate` — parameter validation decorator
  - [ ] `@memoize` — result caching decorator
  - [ ] `@debounce` / `@throttle` — timing decorators
  - [ ] `@sealed` — preventing class extension
  - [ ] Dependency injection pattern with decorators
- Mini-project: Dependency injection container 🚧
  - Build a simple DI container using decorators: `@Injectable()` marks classes, `@Inject()` resolves dependencies; the container registers and instantiates services with correct types

**Useful Resources:**
- [TypeScript 5.0 — Decorators](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-5-0.html#decorators)
- [TC39 Decorators Proposal (GitHub)](https://github.com/tc39/proposal-decorators)
- [TypeScript Handbook — Decorators (experimental)](https://www.typescriptlang.org/docs/handbook/decorators.html)
- [TypeScript 5.2 — Decorator Metadata](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-5-2.html)

---

## Stage 11 — TypeScript with the DOM & Node.js 🚧
- TypeScript and the DOM 🚧
  - [ ] Built-in DOM type definitions (`lib.dom.d.ts`)
  - [ ] `HTMLElement` and its subtypes (`HTMLInputElement`, `HTMLButtonElement`, etc.)
  - [ ] `querySelector` return types and generic overloads
  - [ ] Type assertions with DOM elements (`as HTMLInputElement`)
  - [ ] `Event` types (`MouseEvent`, `KeyboardEvent`, `InputEvent`, `SubmitEvent`, etc.)
  - [ ] Typing event handlers and `addEventListener` callbacks
  - [ ] `EventTarget` and custom events with typed detail (`CustomEvent<T>`)
  - [ ] `document.createElement` generic overloads
  - [ ] Working with `NodeList`, `HTMLCollection`, and iterating typed collections
- DOM utility patterns 🚧
  - [ ] Type-safe `querySelector` wrapper (returns `T | null` with correct subtype)
  - [ ] Type-safe event delegation with generics
  - [ ] Generic DOM component pattern
  - [ ] Typing `dataset` (casting to expected shape)
  - [ ] Typing `FormData` and form element values
- TypeScript with Node.js 🚧
  - [ ] `@types/node` — type definitions for Node.js APIs
  - [ ] Typing `fs`, `path`, `http` module usage
  - [ ] `process.env` typing (augmenting `ProcessEnv`)
  - [ ] Building CLI tools with TypeScript
  - [ ] ESM vs CommonJS in Node.js TypeScript
- TypeScript with build tools 🚧
  - [ ] TypeScript with Vite (native TS support)
  - [ ] TypeScript with Webpack (`ts-loader`, `fork-ts-checker-webpack-plugin`)
  - [ ] TypeScript with esbuild (fast transpilation, no type checking)
  - [ ] TypeScript with SWC
  - [ ] `isolatedModules` flag — restrictions for single-file transpilers
  - [ ] Project references and `composite` for monorepos
- Mini-project: Interactive typed dashboard 🚧
  - Build a vanilla TypeScript dashboard (no frameworks) that fetches data from a public API, renders DOM elements with full type safety, uses typed event handlers, custom events, and generic DOM helpers

**Useful Resources:**
- [TypeScript Handbook — DOM Manipulation](https://www.typescriptlang.org/docs/handbook/dom-manipulation.html)
- [@types/node (npm)](https://www.npmjs.com/package/@types/node)
- [Vite — TypeScript](https://vite.dev/guide/features.html#typescript)
- [TypeScript Handbook — Project References](https://www.typescriptlang.org/docs/handbook/project-references.html)

---

## Summary of Stages

| Stage | Topic | Key Skills | Duration |
|-------|-------|------------|----------|
| 1 | Introduction & Setup | tsc, tsconfig, tooling, project structure | 1 week |
| 2 | Basic Types & Annotations | Primitives, arrays, tuples, inference, `satisfies` | 1-2 weeks |
| 3 | Interfaces & Type Aliases | Interfaces, types, intersection, index signatures | 1-2 weeks |
| 4 | Unions, Enums & Narrowing | Unions, discriminated unions, type guards, enums | 1-2 weeks |
| 5 | Functions with TypeScript | Overloads, `this` typing, callback types | 1-2 weeks |
| 6 | Generics | Constraints, keyof, indexed access, generic patterns | 2 weeks |
| 7 | Classes with TypeScript | Access modifiers, abstract classes, mixins, `override` | 1-2 weeks |
| 8 | Advanced Types | Mapped, conditional, template literal, utility types | 2-3 weeks |
| 9 | Modules & Declaration Files | Type-only imports, .d.ts, @types, augmentation | 1-2 weeks |
| 10 | Decorators & Metadata | TC39 decorators, experimental decorators, DI | 1-2 weeks |
| 11 | DOM & Node.js | DOM types, Node.js typing, build tools | 2-3 weeks |

**Total estimated time: 14-22 weeks (~3-5 months)**

---

## Timeline Breakdown

### Phase 1: TypeScript Foundations (Stages 1-3) — 3-5 weeks
Goal: confidently set up TypeScript projects, understand core types, interfaces, and type aliases.

### Phase 2: Type System Mastery (Stages 4-6) — 4-6 weeks
Goal: command unions, narrowing, generics, and function typing for real-world code.

### Phase 3: OOP & Advanced Types (Stages 7-8) — 3-5 weeks
Goal: use TypeScript classes fluently, master mapped types, conditional types, and utility types.

### Phase 4: Ecosystem & Integration (Stages 9-11) — 4-7 weeks
Goal: understand modules, declarations, decorators, DOM typing, and Node.js integration.

---
*You can adjust the pace and topics as needed during your learning journey.*
*Plan created: February 2026*
