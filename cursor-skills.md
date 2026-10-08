Chaliye 👍 Next topic: **Cursor Skills**.

# 2. Cursor Skills — Interview Ready

## 1. One-line definition

> **“Cursor Skills are reusable, task-specific instructions and workflows that teach the Cursor Agent how to perform a particular type of task consistently.”**

Simple language:

> **Skill = AI ko kisi particular kaam ka reusable process sikha dena.**

---

# 2. Kid-level example 👶

Maan lo tumhare paas ek junior developer hai.

Har baar tumhe bolna padta hai:

> "React component banane se pehle existing components check karo, TypeScript use karo, reusable components use karo, tests likho, lint run karo..."

Har feature par same instructions repeat karna boring hai.

To tum ek **React Development Skill** bana dete ho:

```text
React Feature Skill

1. Existing code inspect karo
2. Similar component find karo
3. Architecture understand karo
4. Plan banao
5. Code implement karo
6. Tests likho
7. TypeScript check karo
8. Lint run karo
```

Ab har baar poora instruction repeat nahi karna.

**Ye Cursor Skill hai.**

---

# 3. Cursor mein Skill kahan hoti hai?

Typically project ke andar:

```text
.cursor/
└── skills/
    └── react-feature-development/
        └── SKILL.md
```

`SKILL.md` ke andar tum AI ko workflow/instructions dete ho.

Example:

```md
---
name: react-feature-development
description: Build React features following project conventions.
---

# React Feature Development

1. Inspect existing architecture.
2. Find reusable components.
3. Understand state management.
4. Create an implementation plan.
5. Implement the feature.
6. Add tests.
7. Run lint and type checking.
8. Summarize the changes.
```

Cursor relevant task ke time is skill ko use kar sakta hai, ya tum explicitly invoke kar sakte ho.

---

# 4. Skill ko kaise use karte hain?

Suppose tumne skill banayi:

```text
react-feature-development
```

Tum Cursor mein bol sakte ho:

```text
/react-feature-development

Create a Product Listing Page with:
- Search
- Filters
- Sorting
- Pagination
```

Cursor skill ke workflow ko follow karega.

Conceptually:

```text
Your Request
     ↓
React Feature Skill
     ↓
Understand
     ↓
Plan
     ↓
Implement
     ↓
Test
     ↓
Validate
```

---

# 5. Skill ka sabse bada benefit

### Without Skill

Har baar:

```text
"Check existing architecture.
Use TypeScript.
Don't add dependencies.
Follow existing patterns.
Write tests.
Run lint..."
```

Repeat 😩

### With Skill

```text
/react-feature-development
```

Bas.

🔥 **Skill = reusable prompt + reusable workflow**

Lekin ek important distinction:

> Skill sirf ek short prompt nahi hoti; ismein detailed workflow, references aur scripts bhi package kiye ja sakte hain.

---

# 6. Real React example

Suppose tumhare project mein 20 developers hain.

Tum chahte ho ki React feature development consistent ho.

Tum skill banaoge:

```text
react-feature-development
```

Instructions:

```text
1. Existing architecture inspect karo
2. Existing component reuse karo
3. Redux pattern follow karo
4. Existing API layer reuse karo
5. New dependency mat add karo
6. TypeScript use karo
7. Loading/error/empty states handle karo
8. Tests add karo
9. ESLint run karo
10. TypeScript check karo
```

Ab koi bhi developer Cursor use kare:

```text
/react-feature-development
```

Aur same development standards follow honge.

---

# 7. Skills mein sirf instructions nahi hote

Ye senior-level point hai.

Skill structure:

```text
react-feature-development/
│
├── SKILL.md
│
├── references/
│   ├── architecture.md
│   └── testing-guidelines.md
│
└── scripts/
    └── validate.sh
```

### `SKILL.md`

AI ko process batayegi.

### `references/`

Additional project knowledge.

Example:

```text
architecture.md
```

mein:

```text
We use:
- Redux Toolkit for global state
- React Query for server state
- MUI for UI
- RTL for testing
```

### `scripts/`

Actual validation scripts.

For example:

```bash
npm run lint
npm run typecheck
npm test
```

So skill becomes:

> **Instructions + Knowledge + Reusable workflow**

---

# 8. Skill vs normal prompt

### Normal prompt

```text
Create a React component.

Use TypeScript.
Follow existing patterns.
Write tests.
Don't add dependencies.
```

Ye ek **one-time instruction** hai.

### Skill

```text
react-component-development
```

Ye instructions **reusable** hain.

```text
Feature 1 → Skill
Feature 2 → Skill
Feature 3 → Skill
Feature 4 → Skill
```

---

# 9. Skill vs Rule — interviewer pooch sakta hai

### Rule

Rule usually:

> **"Always follow this coding guideline."**

Example:

```text
Never use `any`.
Use TypeScript strict mode.
```

### Skill

Skill:

> **"When doing this type of task, follow this complete workflow."**

Example:

```text
When fixing a bug:

1. Reproduce
2. Investigate
3. Find root cause
4. Fix
5. Add regression test
6. Validate
```

### Easy trick 🧠

> **Rule = WHAT to follow**

> **Skill = HOW to perform a task**

---

# 10. Skill + SDD 🔥

Ye tumhare interview mein bahut strong combination hai.

Suppose specification hai:

```text
Product Search Specification
```

Skill:

```text
react-feature-development
```

Ab workflow:

```text
                 SDD
                  ↓
          Product Specification
                  ↓
                 Skill
                  ↓
          Analyze codebase
                  ↓
             Create plan
                  ↓
           Human approves
                  ↓
              Implement
                  ↓
                Test
```

Yaani:

> **SDD tells Cursor what needs to be built.**

> **Skill tells Cursor how we want the task to be performed.**

🔥 Is line ko yaad kar lo.

---

# 11. Skill + AIDLC

Dono ko combine karoge:

```text
AIDLC
 │
 ├── Analyze
 │      ↓
 │   Skill helps analyze
 │
 ├── Ideate
 │      ↓
 │   Skill provides workflow
 │
 ├── Develop
 │      ↓
 │   Skill guides implementation
 │
 ├── Launch
 │      ↓
 │   Skill can guide validation
 │
 └── Curate
        ↓
     Skill can guide debugging
```

So:

> **AIDLC is the broader lifecycle. Skills are reusable workflows that help AI perform specific tasks within that lifecycle.**

---

# 12. Interview example

Interviewer:

> **"How do you use Cursor Skills in your project?"**

Tum:

> **“I use Cursor Skills to standardize repetitive and task-specific development workflows. For example, I can create a React feature-development skill containing instructions to first inspect the existing architecture, identify reusable components, understand state management and API patterns, create an implementation plan, implement incrementally, add tests, and run validation. Instead of repeating these instructions in every prompt, I can invoke the skill when working on a React feature. This helps improve consistency, reduce repetitive prompting, and make AI-assisted development more predictable.”**

🔥 Strong answer.

---

# 13. Agar interviewer deeper pooche

### Q: "Why not just use a prompt?"

Answer:

> **“A prompt is usually specific to a particular interaction, whereas a Skill packages reusable domain knowledge and a repeatable workflow that can be applied across similar tasks.”**

---

### Q: "Can Skills contain project-specific knowledge?"

Answer:

> **“Yes. A Skill can include instructions as well as supporting references and scripts, so the AI can follow project-specific conventions and execute repeatable validation steps.”**

---

### Q: "Give me one Skill you would create."

Answer:

> **“For a React project, I would create a React Feature Development Skill. It would instruct Cursor to inspect the existing architecture, reuse components and API utilities, follow the existing state-management pattern, avoid unnecessary dependencies, add tests, and run TypeScript and lint validation before considering the task complete.”**

---

# 14. 30-second answer — memorize this 🎯

> **“Cursor Skills are reusable, task-specific workflows for the Cursor Agent. I use them when I want AI to follow a consistent process for recurring tasks. For example, I can create a React Feature Development Skill that tells Cursor to inspect the existing codebase, understand the architecture, create an implementation plan, reuse existing components and APIs, implement the feature, add tests, and run validation. This avoids repeating the same instructions in every prompt and makes AI-assisted development more consistent and predictable.”**

---

# 15. 3 golden lines 🧠

Agar interview mein nervous ho jao, ye 3 lines yaad rakhna:

> **1. “Skill is a reusable, task-specific workflow for the AI Agent.”**

> **2. “It helps standardize how recurring tasks are performed.”**

> **3. “For example, I can create a React feature-development skill covering analysis, planning, implementation, testing and validation.”**

### One-line difference yaad rakho:

```text
AIDLC  → AI ko poore lifecycle mein use karna
Skill  → AI ko specific task ka reusable workflow dena
```

Next topic tumhare instruction par **SDD in Cursor** hoga.
