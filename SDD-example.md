
# 8. Cursor mein practical example

Suppose tumhare existing React project mein feature banana hai.

### Step 1 — Specification file

Tum project mein bana sakte ho:

```text
/specs/product-listing.md
```

Usmein:

```md
# Product Listing Specification

## Goal

Build a product listing page.

## Functional Requirements

- Display products
- Search products
- Filter by category
- Sort by price
- Pagination

## UI States

- Loading
- Success
- Empty
- Error

## Technical Requirements

- React
- TypeScript
- Redux Toolkit
- Existing API service

## Constraints

- Do not add new dependencies
- Follow existing project patterns
- Do not modify backend

## Acceptance Criteria

- Search must use 300ms debounce
- Pagination must preserve active filters
- API errors must be displayed to users
- Empty results must show an empty state
```

---

# 9. Ab Cursor ko kya prompt doge?

Cursor mein:

```text
Read /specs/product-listing.md.

First inspect the existing codebase and understand:
- component structure
- state management
- API layer
- routing
- existing reusable components
- testing patterns

Do not write code yet.

Based on the specification and existing architecture,
create an implementation plan.

The plan should include:
1. Files to create
2. Files to modify
3. Component architecture
4. State management changes
5. API integration
6. Testing strategy
7. Potential risks

Do not modify any files.
```

Cursor pehle **plan** dega.

---

# 10. Tum plan review karoge 👀

Suppose Cursor bolta hai:

```text
Create:

ProductListingPage.tsx
ProductFilters.tsx
ProductCard.tsx
productSlice.ts
productApi.ts
```

Tum check karoge:

> "Kya existing project mein already productApi hai?"

Agar hai:

> ❌ New file mat banao.

Tum Cursor ko bolo:

```text
We already have an existing productApi.ts.

Reuse it instead of creating a new API layer.

Update the implementation plan accordingly.
```

🔥 Ye SDD + human review hai.

---

# 11. Phir implementation

Plan approve karne ke baad:

```text
Implement the approved plan.

Follow the specification exactly.

Start with the API integration and Redux state.
Do not modify unrelated files.

After implementation, explain:
- what changed
- why each file was changed
- any assumptions made
```

Cursor code likhega.

---

# 12. Phir tests

Specification mein acceptance criteria already hain.

Ab Cursor ko bolo:

```text
Based on the specification and acceptance criteria,
create React Testing Library tests.

Cover:
- successful product rendering
- search
- debounce behavior
- filtering
- pagination
- loading state
- empty state
- API error state
```

Ab tests directly specification se derived hain.

---

# 13. Ye SDD ka actual magic hai 🔥

Dekho connection:

```text
SPECIFICATION
      │
      ├──→ Implementation
      │
      └──→ Test Cases
```

Matlab:

**Specification ek source of truth ban jaati hai.**

Requirement badli?

Specification update karo.

Phir:

```text
Updated Spec
     ↓
Updated Plan
     ↓
Updated Code
     ↓
Updated Tests
```

---
