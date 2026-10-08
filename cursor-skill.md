Haan. **Cursor Skills** ko tum apne AI developer ko ek **reusable SOP / kaam karne ka tareeka** sikhane jaisa samjho.

> **Rule = "Hamesha ye rule follow karo."**  
> **Skill = "Jab ye type ka kaam aaye, ye poora process follow karo."**

Cursor ke current docs ke according, Skills `SKILL.md` files hoti hain jo specialized workflows, domain knowledge aur scripts ko package kar sakti hain. Cursor unhe relevant hone par automatically discover kar sakta hai, ya tum `/skill-name` se manually invoke kar sakte ho. [Cursor](https://prod.cursor.com/help/customization/skills?utm_source=chatgpt.com)

---

# 1. Sabse pehle: Skill kya hai? 👶

Maan lo tumhare paas ek junior developer hai.

Tum usko baar-baar bolte ho:

> "Jab bhi React component banana ho:
> 1. Existing components dekho
> 2. TypeScript use karo
> 3. Props interface banao
> 4. Reusable component banao
> 5. Accessibility check karo
> 6. Test likho
> 7. Existing design system use karo"

Ab tum ye instructions **ek baar likh kar save** kar dete ho.

Next time:

> "Product card banao."

AI ko pata hai:

```text
React component kaise banana hai
        ↓
Existing patterns dekho
        ↓
TypeScript
        ↓
Reusable
        ↓
Test
        ↓
Accessibility
```

Ye **Skill** hai.

---

# 2. Cursor mein Skill ka structure

Project ke andar:

```text
my-project/
│
├── src/
│
├── package.json
│
└── .cursor/
    └── skills/
        └── react-component/
            └── SKILL.md
```

Cursor officially `.cursor/skills/` aur `.agents/skills/` jaise project-level locations se skills discover karta hai. User-level/global skills ke liye `~/.cursor/skills/` bhi available hai. [Cursor](https://prod.cursor.com/docs/skills?utm_source=chatgpt.com)

---

# 3. SKILL.md kya hoti hai?

Ye basically AI ke liye **instruction manual** hai.

Example:

```md
---
name: react-component
description: Create React components following project conventions and best practices.
---

# React Component Skill

## When to Use

Use this skill when creating or modifying React components.

## Instructions

1. Inspect existing components first.
2. Follow the existing project structure.
3. Use TypeScript.
4. Prefer functional components.
5. Reuse existing components where possible.
6. Avoid introducing new dependencies.
7. Handle loading, error and empty states where applicable.
8. Add appropriate tests.
9. Check accessibility.
10. Do not modify unrelated files.
```

Bas.

Ab Cursor ke paas ek reusable **React development procedure** hai.

---

# 4. Skill manually kaise banayenge?

Current Cursor mein easiest way hai Agent chat mein:

```text
/create-skill
```

Cursor ka built-in `/create-skill` workflow tumse skill ka purpose/workflow lekar `SKILL.md` structure generate kar sakta hai. [Cursor](https://prod.cursor.com/help/customization/skills?utm_source=chatgpt.com)

For example:

```text
/create-skill

Create a skill for building React components in our project.

It should:
- inspect existing patterns
- use TypeScript
- reuse existing components
- avoid new dependencies
- add tests
- check accessibility
- explain changes
```

Cursor skill create karne mein help karega.

---

# 5. Manually bhi bana sakte ho

Windows project:

```text
.cursor/
└── skills/
    └── react-component/
        └── SKILL.md
```

`SKILL.md`:

```md
---
name: react-component
description: Build React components using our project conventions. Use when creating or modifying React components.
---

# React Component Development

## Process

1. Inspect the existing component patterns.
2. Identify reusable components.
3. Understand the existing state management approach.
4. Create the component using TypeScript.
5. Follow existing naming and folder conventions.
6. Avoid new dependencies.
7. Add tests using the existing testing framework.
8. Verify linting and TypeScript.
9. Explain the files changed.
```

---

# 6. Ab skill use kaise karenge?

Do ways hain.

## Way 1 — Manually

Cursor Agent chat mein:

```text
/react-component
```

Phir:

```text
Create a ProductCard component.

Requirements:
- product image
- title
- price
- rating
- Add to Cart button
```

Cursor pehle tumhari `react-component` skill ko load karega aur uske instructions follow karega. Skills ko `/skill-name` se explicitly invoke kiya ja sakta hai. [Cursor](https://prod.cursor.com/help/customization/skills?utm_source=chatgpt.com)

---

# 7. Way 2 — Automatic

Ye aur interesting hai.

Agar tumhari skill ka description hai:

```yaml
description: Build React components using project conventions. Use when creating or modifying React components.
```

Aur tum bolte ho:

> "Create a ProductCard component."

Cursor context dekhkar decide kar sakta hai ki **react-component skill relevant hai**, aur usse use kar sakta hai. Skills default mein agent ko relevant hone par dynamically available hoti hain. [Cursor](https://prod.cursor.com/docs/skills?utm_source=chatgpt.com)

Isliye `description` bahut important hai.

---

# 8. Description ko lightly mat lena

Ye:

```yaml
description: React skill
```

❌ Weak hai.

Better:

```yaml
description: >
  Build and modify React/TypeScript components following existing
  project conventions, reusable component patterns, accessibility
  requirements, and testing practices. Use when creating or modifying
  React components.
```

AI ko clear signal milta hai:

> "Ye skill kab useful hai?"

---

# 9. Tumhare liye ek REAL skill banate hain 🔥

Tum React + MERN developer ho.

Main recommend karunga ki tum ek skill banao:

```text
react-feature-development
```

Folder:

```text
.cursor/
└── skills/
    └── react-feature-development/
        └── SKILL.md
```

Skill:

```md
---
name: react-feature-development
description: >
  Implement React/TypeScript features in the existing application.
  Use when adding or modifying React features, pages, components,
  state management, API integration, or UI behavior.
---

# React Feature Development

## Goal

Implement React features safely while following the existing
architecture and coding conventions.

## Step 1 — Understand

Before modifying code:

- Inspect the repository structure.
- Identify the relevant feature.
- Find similar existing implementations.
- Understand routing.
- Understand state management.
- Understand API integration.
- Identify reusable components.
- Inspect existing tests.

Do not modify files during this step.

## Step 2 — Plan

Create an implementation plan containing:

- Files to create
- Files to modify
- Component structure
- State changes
- API changes
- Testing strategy
- Potential risks

Wait for approval before large changes.

## Step 3 — Implement

Follow the approved plan.

Rules:

- Use TypeScript.
- Follow existing naming conventions.
- Reuse existing components.
- Reuse existing API utilities.
- Do not introduce new dependencies unless required.
- Do not modify unrelated files.

## Step 4 — Testing

Add or update tests for:

- happy path
- loading state
- error state
- empty state
- user interactions
- important edge cases

Use the project's existing testing framework.

## Step 5 — Validation

Run:

- TypeScript check
- ESLint
- relevant tests
- build if appropriate

## Step 6 — Summary

Explain:

- what changed
- why it changed
- files modified
- tests added
- validation results
- any assumptions
```

Ab tumhare paas ek **mini React senior developer SOP** hai.

---

# 10. Ab real example

Tum Cursor mein bolo:

```text
/react-feature-development

Build a product listing page.

Requirements:
- Product search
- Category filter
- Price filter
- Sorting
- Pagination
- Loading state
- Empty state
- Error state
```

Skill Cursor ko batayegi:

```text
पहले:
Understand
   ↓
Plan
   ↓
Approval
   ↓
Implement
   ↓
Test
   ↓
Validate
```

Tumhe har baar ye 20 lines prompt mein nahi likhni padengi.

🔥 **That's the biggest benefit of Skills.**

---

# 11. Skill mein scripts bhi rakh sakte ho

Ye aur powerful feature hai.

Structure:

```text
.cursor/
└── skills/
    └── react-feature-development/
        ├── SKILL.md
        ├── scripts/
        │   └── validate.sh
        ├── references/
        │   └── architecture.md
        └── assets/
```

Cursor Skills optional `scripts/`, `references/`, aur `assets/` directories support karti hain. [Cursor](https://prod.cursor.com/docs/skills?utm_source=chatgpt.com)

For example:

```text
scripts/
└── validate.sh
```

```bash
npm run lint
npm run typecheck
npm test -- --run
```

Aur `SKILL.md` mein:

```md
## Validation

After implementation, run:

scripts/validate.sh
```

AI ke paas instructions + actual executable workflow dono aa gaye.

---

# 12. References ka use

Suppose tumhare project mein bahut bada architecture document hai.

Instead of `SKILL.md` mein 500 lines likhna:

```text
references/
├── architecture.md
├── api-guidelines.md
└── testing-guidelines.md
```

`SKILL.md`:

```md
Before implementing a feature:

1. Read references/architecture.md
2. Read references/api-guidelines.md
3. Follow the testing guidelines from references/testing-guidelines.md
```

Cursor skills resources ko on-demand load kar sakti hain, jisse unnecessary context har baar nahi bharna padta. [Cursor](https://cursor.com/docs/skills?trk=article-ssr-frontend-pulse_little-text-block\&utm_source=chatgpt.com)

---

# 13. Skill vs Rule — ye interview mein pooch sakte hain

Bahut important.

### Rule

> **"Hamesha TypeScript use karo."**

```text
Rule
 ↓
Always apply
```

### Skill

> **"Jab React feature banana ho, ye complete process follow karo."**

```text
Skill
 ↓
Relevant task aaya
 ↓
Process follow karo
```

Cursor docs bhi isi distinction ko use karti hain: rules short/persistent coding guidance ke liye, skills detailed reusable multi-step workflows ke liye. [Cursor](https://prod.cursor.com/help/customization/skills?utm_source=chatgpt.com)

---

# 14. Ek simple example

### Rule

```text
Never use `any`.
```

Ye short instruction hai.

### Skill

```text
React Feature Development

1. Analyze requirement
2. Inspect architecture
3. Find reusable components
4. Create implementation plan
5. Implement
6. Add tests
7. Run lint
8. Run TypeScript
9. Run tests
10. Summarize changes
```

Ye **workflow** hai.

So:

> **Rule = What to follow**  
> **Skill = How to do a particular job**

---

# 15. Skill vs SDD

Tumne abhi SDD bhi padha tha.

Dono ko connect karo:

### SDD

```text
Specification
     ↓
Plan
     ↓
Code
     ↓
Test
```

### Skill

Skill AI ko **ye process repeatably karna sikhati hai**.

```text
React Feature Skill
        ↓
Read specification
        ↓
Analyze codebase
        ↓
Create plan
        ↓
Implement
        ↓
Test
        ↓
Validate
```

So tum ek skill bana sakte ho:

> **"SDD React Feature Development"**

🔥 Ye tumhare interview ke liye excellent practical example hai.

---

# 16. Tumhare project mein main kaunsi Skills banaunga?

Tumhare React/MERN background ke hisaab se:

```text
.cursor/
└── skills/
    │
    ├── react-feature-development/
    │   └── SKILL.md
    │
    ├── bug-fix/
    │   └── SKILL.md
    │
    ├── code-review/
    │   └── SKILL.md
    │
    ├── api-integration/
    │   └── SKILL.md
    │
    ├── react-testing/
    │   └── SKILL.md
    │
    ├── performance-optimization/
    │   └── SKILL.md
    │
    └── security-review/
        └── SKILL.md
```

Then:

```text
/bug-fix
```

or:

```text
/react-testing
```

or:

```text
/performance-optimization
```

---

# 17. Ek powerful Bug Fix Skill

For example:

```md
---
name: bug-fix
description: >
  Investigate and fix bugs in the existing application.
  Use when debugging errors, unexpected UI behavior, API failures,
  regressions, or production issues.
---

# Bug Fix Workflow

## 1. Reproduce

Understand:
- expected behavior
- actual behavior
- reproduction steps

## 2. Investigate

Inspect:
- relevant components
- hooks
- state management
- API calls
- error handling
- recent changes

Do not modify code yet.

## 3. Root Cause

Identify the root cause before implementing a fix.

Do not make speculative changes.

## 4. Fix

Make the smallest safe change.

Do not modify unrelated code.

## 5. Test

Add or update regression tests.

## 6. Validate

Run relevant:
- tests
- lint
- type checking

## 7. Summary

Explain:
- root cause
- fix
- affected files
- tests
```

Ab production bug aaya:

```text
/bug-fix

Product API returns 500 and the UI crashes.
```

Cursor ko workflow already pata hai.

---

# 18. `paths` bhi important hai

Suppose tum chahte ho ki React component skill sirf `.tsx` files ke liye relevant ho.

```yaml
---
name: react-component-patterns
description: React component conventions for this project.
paths:
  - "**/*.tsx"
---
```

Cursor `paths` ke through skill ko specific file patterns tak scope kar sakta hai. [Cursor](https://prod.cursor.com/docs/skills?utm_source=chatgpt.com)

---

# 19. Skill ko sirf manually chalana ho?

Kabhi tum nahi chahte ki AI automatically use kare.

Then:

```yaml
---
name: production-deploy
description: Deploy the application to production safely.
disable-model-invocation: true
---
```

Ab tum manually:

```text
/production-deploy
```

karoge.

Cursor docs ke according `disable-model-invocation: true` skill ko explicit invocation tak restrict karta hai. [Cursor](https://cursor.com/docs/skills?trk=article-ssr-frontend-pulse_little-text-block\&utm_source=chatgpt.com)

Production deployment ke liye ye sensible guardrail ho sakta hai.

---

# 20. Final mental model 🧠

Cursor ko ek **junior developer** samjho.

### Rule

Tum usko bolte ho:

> "Hamesha helmet pehenna."

### Skill

Tum usko bolte ho:

> "Jab bike repair karni ho, ye 10-step process follow karna."

### SDD

Tum usko bolte ho:

> "Pehle blueprint padho, phir plan banao, phir ghar banao."

### AIDLC

Tum usko bolte ho:

> "AI ko requirement se production monitoring tak poore lifecycle mein use karo."

Aur sab combine:

```text
                 AIDLC
                   │
                   ↓
                  SDD
                   │
             Specification
                   │
                   ↓
              Cursor Agent
                   │
          ┌────────┴────────┐
          ↓                 ↓
        Rules             Skills
                            │
                    Reusable Workflow
                            │
          ┌─────────────────┼─────────────────┐
          ↓                 ↓                 ↓
    React Feature       Bug Fix          Code Review
          ↓                 ↓                 ↓
       Plan → Code → Test → Validate
```

### Interview mein ekdum simple answer:

> **"Cursor Skills are reusable, task-specific instructions and workflows for the Agent. Instead of repeatedly explaining how I want a particular task to be performed, I create a `SKILL.md` containing the workflow, conventions, and optionally scripts or references. For example, I can create a React feature-development skill that tells Cursor to first inspect the codebase, understand the architecture, create an implementation plan, implement incrementally, add tests, and run validation. I can invoke it using `/react-feature-development`, or Cursor can automatically use it when the task matches the skill description."** [Cursor](https://prod.cursor.com/help/customization/skills?utm_source=chatgpt.com)

**Tumhare case mein next best step hai:** ek **real `react-feature-development` Skill + SDD workflow** banana aur phir usse Product Listing Page par apply karna. Isse tum **Skills + SDD + AIDLC + good prompting** chaaro ek hi practical example se samajh jaoge.
