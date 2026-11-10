No — your README should be **one file for one course**, not a bundle of drafts. The two drafts are separate programmes; each gets its own repo and its own README.

Since we're currently building **Draft 2**, the README above is already correct as-is. Here it is again, clean, ready to drop in as `README.md` at the repo root:

```markdown
# Inventory Manager — Frontend-Focused Programme (Draft 2)

A beginner programme that goes deep on the frontend foundations: JavaScript,
TypeScript, React, Next.js, and frontend principles. You build one real
application — an Inventory Management System — from a static shell to a
deployed, accessible, multi-page app.

This is **Draft 2**: simplified, clear, frontend-first. It deliberately excludes
databases, authentication, deep testing, and CI. Those belong to Draft 1, the
full programme, which you can continue into afterwards.

---

## What this course is

A hands-on frontend engineering programme. You will:

- Learn JavaScript and TypeScript by reading and writing real code, not by
  memorising syntax lists.
- Learn React by building components, then pulling them apart to see what
  React does underneath.
- Learn Next.js by building a multi-page application, then seeing what the
  framework automates.
- Learn frontend principles — routing, accessibility, responsive layout —
  that outlive any framework.
- Finish with a deployed, working application you can show someone.

**One project, eighteen classes, built incrementally.** Nothing is thrown away.
Every class adds to the last.

---

## What this course is not

- **Not a JavaScript encyclopedia.** We cover the language thoroughly, but
  every concept is introduced when it appears in code you are writing. You
  will not memorise the entire language before building.
- **Not a backend course.** We touch API routes minimally in Class 13, because
  a frontend developer must understand how data arrives. But this is not
  where you learn databases, auth, or server architecture.
- **Not a "watch and copy" course.** Every class has exercises, drills, and an
  answer branch to compare against. You move when you have done the work.
- **Not total coverage of software engineering.** See "What you will not learn"
  below. This course is honest about its boundaries.

---

## Who this is for

- Complete beginners with no programming experience.
- Career changers who want a solid frontend foundation before going further.
- Anyone who has used React or Next.js tutorials but cannot explain what the
  framework is doing underneath.

**What you need before Class 01:** nothing. The course starts at `const`.

**What you need installed:** see "Setup" below.

---

## The stack

| Tool | What it is | Why we use it |
|---|---|---|
| **Bun** | Runtime + package manager | Fast; runs `.ts` files directly; installs dependencies |
| **Next.js** | React framework | File-based routing, server rendering, deployment-ready |
| **React** | UI library | Component model, the industry standard for frontend |
| **TypeScript** | Typed JavaScript | Catches bugs in the editor, not in production |
| **Tailwind CSS** | Utility-first CSS | Fast styling, no naming, only the CSS you use |
| **Git + GitHub** | Version control | Track changes, branch, compare, share |

Later in the course: **shadcn/ui** (pre-built accessible components) in Class 13.

---

## Setup (do this once, before Class 01)

### 1. Install Bun

**macOS / Linux:**
```bash
curl -fsSL https://bun.sh/install | bash
```

**Windows (PowerShell):**
```powershell
powershell -c "irm bun.sh/install.ps1 | iex"
```

Verify:
```bash
bun --version
```
You should see a version number like `1.1.x`.

### 2. Install Node.js (optional but recommended)

Bun handles everything for this course, but real projects sometimes require
Node.js. Install it with **fnm** (a Node version manager):

**Windows:**
```powershell
winget install Schniz.fnm
fnm env --use-on-cd --shell powershell | Out-String | Invoke-Expression
fnm install --use 26
node -v   # should print a version
npm -v    # should print a version
```

**macOS / Linux:**
```bash
curl -fsSL https://fnm.vercel.app/install | bash
fnm install --use 26
node -v
```

**Why this matters:** most tutorials and companies use `npm` and `node`. You
need to recognise them even though we use `bun`. Commands are equivalent:
`npm install` ↔ `bun add`, `npm run dev` ↔ `bun run dev`.

### 3. Install VS Code

Download from https://code.visualstudio.com.

Install these extensions:
- **Prettier** (formats your code on save)
- **Tailwind CSS IntelliSense** (autocompletes Tailwind classes)

### 4. Clone the project

```bash
git clone <your-repo-url> inventory-manager
cd inventory-manager
```

You will be told which branch to check out for each class (see "How to use
this repo" below).

---

## How to use this repo

### Branches

Every class lives on its own branch:
- `class-01` — the project state at the end of Class 1
- `class-02` — the project state at the end of Class 2
- ...
- `class-18` — the final state
- `main` — the final deployed version

### Starting a class

```bash
git checkout class-0N
bun install
bun run dev
```

Then read `classes/class-0N/notes.md`, do `classes/class-0N/exercise.md`,
and finish with `classes/class-0N/under-the-hood.md`.

### Doing the work

Do not work on the class branch directly. Create your own branch off it:

```bash
git checkout -b my-attempt-class-01 class-01
```

Do the exercise. Then compare your work to the answer:

```bash
git diff class-01..my-attempt-class-01
```

The diff shows exactly what you got right and what you missed.

### The rule

**Do not open the answer branch until you have attempted the exercise.**

The answer exists so you can compare, not copy. If you copy, you will pass the
exercise and fail the interview.

---

## The class folder

Every class folder contains the same four files:

| File | What it is | When to read it |
|---|---|---|
| `notes.md` | The lesson: theory, scenarios, what we build and why | First |
| `language-reference.md` | Deep breakdown of every JS/TS syntax in the code | Alongside notes.md |
| `exercise.md` | Language drills + the feature build | After notes |
| `under-the-hood.md` | What the framework is doing beneath the code | After the exercise |

The `language-reference.md` is your long-term handbook. By Class 6, it is large
enough to answer most "what does this syntax mean?" questions.

The `under-the-hood.md` is what separates you from developers who can only
use frameworks. Every class adds one mechanism you can explain in an interview.

---

## The 18 classes

### Section 1 — The Language (Classes 1–6)
Deep JavaScript and TypeScript, anchored in real code.

1. How the web works + project setup + first TSX
2. Variables, types, functions, arrays, objects
3. TypeScript: interfaces, unions, typed functions
4. State, events, controlled inputs, useState
5. Lists, `.map` in JSX, conditional rendering, keys
6. Async JS, fetch, promises, loading/error states

### Section 2 — React Depth (Classes 7–10)
Component thinking and the React model.

7. Component composition, props, children
8. Lifting state, derived state, controlled vs uncontrolled
9. Effects, useEffect, cleanup, avoiding common bugs
10. Forms in depth: validation, error handling, user feedback

### Section 3 — Next.js & Frontend Principles (Classes 11–16)
The framework, then the principles that outlive it.

11. App Router: pages, layouts, navigation, links
12. Server vs client components, when to use which
13. API routes (minimal backend), data fetching patterns, shadcn/ui
14. Routing theory: client-side vs server-side, history, URLs
15. Accessibility, semantic HTML, keyboard navigation
16. Responsive design, layout principles, CSS in depth

### Section 4 — Git, AI, and Shipping (Classes 17–18)
The minimum surrounding workflow.

17. Git flow: branches, commits, compare, push
18. AI-assisted frontend dev + deploy to Vercel

---

## What you will be able to do

By the end of Class 18, you will be able to:

- Read and write JavaScript and TypeScript fluently.
- Explain what React is doing beneath the components — virtual DOM, state,
  effects, hydration.
- Build a multi-page Next.js app with routing, layouts, and navigation.
- Fetch data, handle loading and error states, and display it.
- Build accessible, responsive, keyboard-navigable interfaces.
- Use Git to branch, commit, compare, and push.
- Deploy a real application to the internet.
- Use AI tools responsibly as a coding assistant, not a crutch.
- Explain the difference between manual implementation and framework
  shortcuts — and debug either.

---

## What you will not learn (honest scope)

This is Draft 2. It deliberately excludes:

- **Databases** — how to store and query data permanently.
- **Authentication** — how to log users in and verify who they are.
- **Deep testing** — only the minimum needed to prove a component works.
- **Team Git workflow** — forks, rebase, PR review, CI/CD.
- **Advanced TypeScript** — generics, utility types, discriminated unions.
- **Backend depth** — validation, error handling, background jobs, security.
- **System design** — scalability, trade-offs, architecture at scale.

These are not forgotten — they are **Draft 1**, the full programme. You can
continue into Draft 1 after completing Draft 2, with a strong frontend
foundation already in place.

If you expect total coverage of software engineering from this course, you
will be disappointed. If you expect deep, clear frontend mastery that prepares
you for the next step, you are in the right place.

---

## The programme philosophy

### Manual vs framework

Every concept is taught twice:

- **Manual:** the raw mechanism. What the browser actually receives. What a
  function call actually does. What `fetch` actually sends.
- **Framework:** how React, Next.js, or Tailwind does it for you.

You need both. Framework-only developers cannot debug. Manual-only developers
cannot ship at industry speed. This course refuses to let you be either.

### Theory behind the practice

Every class includes:
- **The theory:** what this concept is, why it exists, what problem it solves.
- **A real-life scenario:** a story that makes the concept concrete. Maria's
  candle shop is the running scenario for the inventory app; other scenarios
  appear in drills and exercises.
- **The practice:** write the code, run it, see it work, compare to the answer.

Nothing is taught in the abstract. Nothing is practiced without understanding
why it matters.

### Build one thing, incrementally

You do not build five throwaway projects. You build **one** project over
eighteen classes:
- Class 1: a static shell
- Class 2: an interactive form
- Class 6: data from a server
- Class 11: multiple pages
- Class 15: accessible to screen readers
- Class 16: responsive on every screen
- Class 18: deployed and live

At every step, the project is something you can show someone. At the end, it
is something you can put in a portfolio.

---

## Common problems

### `bun run dev` does nothing

Make sure you are in the project root (where `package.json` lives). Check that
bun is installed (`bun --version`). Look at the terminal output for errors.

### The page is blank

Open the browser dev tools (F12) and check the Console tab. A React error
will be shown there. Most blank pages are caused by a typo in a component name
or an unclosed tag.

### My changes do not appear

Save the file. Next.js hot-reloads on save. If it still doesn't update, check
the terminal for a compilation error.

### I broke something and want to start over

```bash
git checkout class-0N -- .
```

This resets all files to the class branch state. Your work is lost. Use only
when stuck.

### I want to see the answer

```bash
git diff class-0N..my-attempt-class-0N
```

Or check out the answer branch and look at it:

```bash
git checkout class-0N
```

Remember: read, close, rewrite from memory.

---

## Resources

- **MDN Web Docs** — the reference for everything about the web (HTML, CSS,
  JavaScript, browser APIs). https://developer.mozilla.org
- **React docs** — https://react.dev
- **Next.js docs** — https://nextjs.org/docs
- **Tailwind docs** — https://tailwindcss.com/docs
- **TypeScript handbook** — https://www.typescriptlang.org/docs/handbook

When you are stuck for more than 15 minutes, read the docs first. If the docs
don't help, ask AI to explain — but never paste code you don't understand.

---

## After this course

You will be ready for:
- **Draft 1** — the full programme, which adds database, auth, testing, team
  Git, and a capstone.
- **A junior frontend job** — you can build, deploy, and explain a React /
  Next.js frontend.
- **Self-directed learning** — you have the vocabulary and the mindset to
  learn new tools on your own.

The goal is not to know everything. The goal is to know enough to keep learning
without being afraid of what you don't know yet.

---

## One final note

You are not learning to write code. You are learning to **understand problems,
design solutions, and ship working software**.

The code is the medium. The thinking is the point.

Learn. Build. Test. Deploy.
```

---

This is your README. One file, one course, no draft mixing. Draft 1's README would be a separate document for a separate repo when you build that programme.

Say **"Draft 2, Class 2"** when ready.