# 3. SDD in Cursor — Interview Ready

Ab **SDD = Spec-Driven Development** ko interview perspective se solid karte hain.

## 1. One-line definition 🎯

> **“Spec-Driven Development means defining clear requirements, expected behavior, constraints and acceptance criteria in a specification before asking AI to implement the feature.”**

Simple:

> **“Pehle AI ko clearly batate hain kya banana hai aur expected behavior kya hai, phir code likhwate hain.”**

---

# 2. Kid-level example 👶

Tum kisi carpenter ko bolo:

> ❌ “Table bana do.”

Wo poochega:

- Kitni badi?
- Kitne drawers?
- Kaunsa material?
- Kitni height?
- Color?
- Kitna weight?

Ab tum blueprint de do:

```text
Table:
- Width: 5 feet
- Height: 3 feet
- 3 drawers
- Wooden
- Brown
- Strong enough for 50kg
```

Ab carpenter ko guess nahi karna padega.

**Ye specification hai.**

Cursor mein bhi same concept:

```text
Requirement
     ↓
Specification
     ↓
Cursor understands
     ↓
Plan
     ↓
Code
     ↓
Test
```

---

# 3. Cursor mein problem kya hoti hai without SDD?

Tum Cursor ko bolte ho:

```text
Build a product listing page.
```

AI ko bahut saari cheezein guess karni padengi:

```text
Search kaise?
Pagination?
Redux?
API?
Loading?
Error?
Empty state?
Performance?
Testing?
```

AI apni assumption bana lega.

Problem:

> **AI-generated code technically correct ho sakta hai, but business requirement ke according wrong ho sakta hai.**

---

# 4. SDD approach

Pehle specification:

```md
# Product Listing Specification

## Goal

Allow users to browse and search products.

## Requirements

- Display products
- Search products
- Category filter
- Price filter
- Sorting
- Pagination

## UI States

- Loading
- Success
- Empty
- Error

## Constraints

- React + TypeScript
- Use existing Redux architecture
- Use existing API layer
- No new dependencies

## Acceptance Criteria

- Search should debounce API calls by 300ms
- Filters should remain selected during pagination
- API errors should be shown to the user
- Empty results should show an empty state
```

Ab Cursor ko bolo:

> **“Read this specification and create an implementation plan. Don't modify any files yet.”**

---

# 5. SDD ka golden workflow

Interview mein ye flow explain karna:

```text id="8kq4c8"
SPECIFICATION
      ↓
UNDERSTAND
      ↓
PLAN
      ↓
HUMAN REVIEW
      ↓
IMPLEMENT
      ↓
TEST
      ↓
VALIDATE
```

### Yaad rakhne ki trick:

> **Spec → Plan → Code → Test**

---

# 6. Specification mein kya hona chahiye?

Ek good specification mein generally:

### 1. Goal

> Feature kyu bana rahe hain?

### 2. Functional requirements

> Feature kya karega?

### 3. Non-functional requirements

> Performance/security/accessibility etc.

### 4. Constraints

> Kya nahi karna hai?

### 5. Expected behavior

> Different situations mein application kaise behave karega?

### 6. Acceptance criteria

> Feature successful kab maana jayega?

---

# 7. Acceptance Criteria — very important 🔥

Suppose requirement:

> User can search products.

Acceptance criteria:

```text
Given:
User is on product listing page.

When:
User enters "laptop".

Then:
API should be called after 300ms debounce.

And:
Matching products should be displayed.
```

Another:

```text
Given:
Search returns no products.

Then:
Show "No products found".

Do not show an empty product grid.
```

AI ke liye ye bahut powerful hai because:

> **Acceptance criteria AI ko exact expected behavior batati hai.**

---

# 8. Cursor mein actual workflow

Tum Cursor ko first prompt doge:

```text
Read the product listing specification.

Inspect the existing codebase.

Understand:
- component structure
- routing
- state management
- API layer
- reusable components
- testing approach

Do not modify files.

Create an implementation plan.
```

Cursor plan dega:

```text
1. Modify ProductListingPage
2. Reuse ProductCard
3. Add search state
4. Update product API
5. Add debounce
6. Add filter state
7. Add pagination
8. Add tests
```

Tum plan review karoge.

Agar plan correct hai:

```text
Proceed with the approved plan.

Implement incrementally.

Follow the specification exactly.
Do not modify unrelated files.
```

---

# 9. Human approval 🔥

Ye Senior/Lead level point hai.

> **“I don't let the AI immediately modify the code. For complex features, I first ask it to analyze the specification and create an implementation plan. I review that plan and then allow implementation.”**

Flow:

```text
AI
 ↓
Plan
 ↓
Human Review
 ↓
Approve
 ↓
AI Implementation
```

This reduces unwanted changes.

---

# 10. SDD ka biggest benefit

### Without SDD

```text
Prompt
 ↓
AI assumptions
 ↓
Code
 ↓
Developer discovers wrong behavior
 ↓
Rework
```

### With SDD

```text
Specification
 ↓
Clear requirements
 ↓
Plan
 ↓
Review
 ↓
Code
 ↓
Test against specification
```

Result:

> **Less ambiguity + less rework + more predictable AI output.**

---

# 11. SDD + Testing 🔥

Ye important connection hai:

```text
Specification
      │
      ├────────→ Implementation
      │
      └────────→ Test Cases
```

Suppose specification says:

```text
Search must debounce 300ms.
```

Then test:

```text
User types "lap"
 ↓
API should NOT immediately execute
 ↓
Wait 300ms
 ↓
API executes
```

So:

> **Specification becomes the source of truth for both implementation and testing.**

---

# 12. SDD + Cursor Skills

Ye difference interviewer ko impress karega:

### SDD tells:

> **WHAT to build**

### Skill tells:

> **HOW to perform the task**

Example:

```text
SDD:
Product search should debounce 300ms.

Skill:
1. Inspect existing search patterns
2. Reuse existing hooks
3. Follow project conventions
4. Add tests
5. Run validation
```

Together:

```text
Specification
     ↓
What should be built
     +
Skill
     ↓
How AI should build it
```

🔥 Very strong conceptual point.

---

# 13. SDD + AIDLC

Ye bhi clear rakho:

### AIDLC

AI ko **whole lifecycle** mein use karna:

```text
Analyze
Ideate
Develop
Launch
Curate
```

### SDD

Development se pehle **clear specification** define karna:

```text
Spec
 ↓
Plan
 ↓
Implement
 ↓
Test
```

So you can say:

> **“I see SDD as a way to make AI-assisted development more predictable, while AIDLC is the broader approach of using AI throughout the development lifecycle.”**

---

# 14. Interview question: "Why is SDD important with AI?"

Excellent answer:

> **“AI can generate code very quickly, but if the requirement is ambiguous, it can also make incorrect assumptions very quickly. SDD reduces that ambiguity by giving the AI a clear specification, constraints and acceptance criteria before implementation. This makes the generated solution more predictable and reduces rework.”**

🔥 Ye answer yaad karna.

---

# 15. Interview question: "How do you implement SDD in Cursor?"

Answer:

> **“For a complex feature, I first create a specification containing the goal, functional requirements, expected behavior, constraints and acceptance criteria. I then ask Cursor to read the specification and inspect the existing codebase without making changes. Cursor creates an implementation plan, which I review. After approval, I ask it to implement the plan incrementally. Finally, I validate the implementation against the specification using automated tests, TypeScript checks, linting and code review.”**

---

# 16. Interview mein practical example

Interviewer:

> **“Give me an example.”**

Tum:

> **“Suppose I need to add product search to an existing React application. Instead of directly asking Cursor to implement search, I first define a specification: search should support keyword input, 300ms debounce, loading, empty and error states, and should preserve existing filters. I then ask Cursor to inspect the existing API and state-management architecture and create a plan without modifying files. After reviewing the plan, I approve the implementation. Cursor then implements the feature and generates tests based on the acceptance criteria. Finally, I validate it through TypeScript, linting, automated tests and code review.”**

---

# 17. Common mistake ❌

Don't say:

> **“SDD means I create a document and give it to Cursor.”**

That's incomplete.

Better:

> **“The specification acts as a source of truth throughout implementation and validation.”**

Because SDD isn't just documentation.

It's:

```text
Specification
     ↓
Planning
     ↓
Implementation
     ↓
Testing
     ↓
Validation
```

---

# 18. 30-second answer 🎯

Isko memorize kar sakte ho:

> **“SDD, or Spec-Driven Development, means defining the expected behavior, requirements, constraints and acceptance criteria before implementation. In Cursor, I use the specification as the source of truth. I first ask Cursor to understand the specification and inspect the existing codebase, then create an implementation plan without changing files. I review the plan, approve it, and then let Cursor implement the feature incrementally. Finally, I validate the implementation against the specification through tests, type checking, linting and code review. This reduces ambiguity, AI assumptions and rework.”**

---

# 19. 3 Golden Lines 🧠

Agar interview mein kuch yaad na rahe:

> **1. “SDD means specification first, implementation second.”**

> **2. “The specification becomes the source of truth for implementation and testing.”**

> **3. “In Cursor, I prefer plan-first implementation: analyze → plan → human review → code → test.”**

### Final mental model:

```text
AIDLC  → AI ko WHOLE lifecycle mein use karna

Skills → AI ko specific TASK ka reusable workflow dena

SDD    → AI ko WHAT + expected behavior clearly define karna
```
