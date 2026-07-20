# TypeScript — Tech Lead Learning Path (QA Automation Focus)

An accelerated, high-signal learning path for an experienced **QA Tech Lead** transitioning to or standardizing a team on TypeScript. Since you already know OOP, test automation, and general programming concepts, this guide skips basic syntax and focuses entirely on **advanced type systems, async patterns, and framework architecture**.

---

## 1. Advanced Type Systems for Test Frameworks (~4h)

Skip basic types (`string`, `number`, `boolean`). Focus on types that make test data builders, POMs, and API clients type-safe and refactor-resilient.

- **Generics & Utility Types (`Partial`, `Pick`, `Omit`, `Record`, `ReturnType`)**
  - Use `Partial<Payload>` for API PATCH requests or optional test overrides.
  - Use `Omit<User, 'id'>` when generating POST request creation payloads.
  - *Read:* [TS Handbook: Utility Types](https://www.typescriptlang.org/docs/handbook/utility-types.html) & [Generics](https://www.typescriptlang.org/docs/handbook/2/generics.html)

- **Union Types, Discriminated Unions & Type Guards**
  - Essential for typing polymorphic API responses (e.g., handling `{ status: 'success', data: ... } | { status: 'error', error: ... }`).
  - *Read:* [Narrowing & Type Guards](https://www.typescriptlang.org/docs/handbook/2/narrowing.html)

- **Total TypeScript — Advanced Type Magic**
  - Matt Pocock's concise, high-level exercises on type inference and generics.
  - *Practice:* [Total TypeScript Tutorials](https://www.totaltypescript.com/tutorials)

---

## 2. Asynchronous Patterns & Error Handling (~2h)

Test automation is 100% asynchronous. As a Tech Lead, you need to establish patterns that prevent unhandled promise rejections, race conditions, and flaky execution.

- **Async/Await, Promise.all, & Promise.allSettled**
  - Use `Promise.all` for parallel API data setup/teardown in test hooks.
  - Handling asynchronous loops properly without breaking execution order.
  - *Read:* [TS Async Deep Dive](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-1-7.html#async-functions)

- **Runtime Schema Validation (Zod)**
  - TypeScript types disappear at runtime. Use **Zod** to validate live API responses and environment variables, failing tests immediately with clear errors if contracts change.
  - *Read & Implement:* [Zod Official Docs](https://zod.dev/)

---

## 3. Architecture, Tooling & Strictness (~2h)

Standardizing repository configurations and enforcing type safety across the QA team.

- **Strict `tsconfig.json` Setup for Test Runners**
  - Enforce `strict: true`, `noImplicitAny`, and `strictNullChecks` to catch `undefined` locator/API errors at compile time rather than during CI test runs.
  - *Reference:* [TSConfig Cheat Sheet](https://www.totaltypescript.com/tsconfig-cheat-sheet)

- **Path Aliases & Module Resolution**
  - Configure `@pages/*`, `@fixtures/*`, `@helpers/*` in `tsconfig.json` to eliminate messy relative imports like `../../../../helpers/auth`.
  - *Read:* [Module Resolution & Path Mapping](https://www.typescriptlang.org/docs/handbook/module-resolution.html#path-mapping)

---

## 4. AI-Assisted TypeScript Development & Refactoring (~2h)

As a Tech Lead, learning how to leverage AI coding assistants (GitHub Copilot, Cursor, Claude) to accelerate framework development and enforce team type standards is essential.

- **AI-Driven Type Generation & Schema Translation**
  - Learn to prompt AI to automatically convert JSON API payloads, Swagger/OpenAPI specs, or GraphQL docs into strict TypeScript interfaces and Zod validation schemas.
  - *Practice:* Use prompt patterns like *"Generate a Zod schema and inferred TypeScript type from this JSON payload, enforcing strict email and UUID formatting."*

- **AI for Complex Type Troubleshooting & Refactoring**
  - Leverage AI assistants to decode complex TypeScript compiler errors, write advanced Generic constraints, or refactor legacy `any`/`unknown` types into type-safe discriminated unions.
  - *Read & Practice:* [GitHub Copilot for TypeScript Best Practices](https://github.blog/developer-skills/github-copilot/how-to-use-github-copilot-for-typescript/)

---

## Tech Lead Summary (~10 hours total)

| Module | Hours | Tech Lead Value |
| :--- | :--- | :--- |
| **1. Advanced Types & Generics** | ~4h | Build reusable, type-safe Page Objects, test fixtures, and API clients |
| **2. Async Patterns & Zod** | ~2h | Parallel test data setup and runtime API contract validation |
| **3. Architecture & TSConfig** | ~2h | Enforcing strict team coding standards and clean project imports |
| **4. AI-Assisted Development** | ~2h | Accelerating type generation from specs and AI-driven type refactoring |
