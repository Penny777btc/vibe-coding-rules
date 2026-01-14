# Vibe Coding Rules

> Your personal coding rules library - Help AI assistants avoid repeating mistakes

A knowledge management system for [Vibe Coding](https://en.wikipedia.org/wiki/Vibe_coding). Collect lessons learned during development, so AI coding assistants (Claude Code, Cursor, Windsurf, etc.) can reference your rules and avoid making the same mistakes twice.

---

## Quick Start

### Step 1: Fork this repo

Click the **Fork** button to create your own copy.

### Step 2: Set up a new project

Copy this prompt to your AI assistant when starting a new project:

```
Set up my coding rules system:

1. Read my rules: https://github.com/YOUR_USERNAME/vibe-coding-rules
   - Read MASTER_RULES.md for core rules
   - Read by-stack/ files matching this project's tech stack

2. Create CLAUDE.md in project root with:
   - Link to my rules repo
   - Project name, tech stack, description
   - Instruction: "After fixing bugs, ask if I want to record it"

3. Create empty LESSONS_LEARNED.md for recording issues

4. From now on, after fixing any bug:
   - Ask me: "Record this issue?"
   - If yes, append to LESSONS_LEARNED.md
   - Format: title, date, type, cause, solution, code example

5. When I say "sync to central rules", first review:
   - Universality: Will other projects face this?
   - Quality: Has code examples? Root cause analysis?
   - Duplicates: Already exists in rules repo?
   - Only sync if passes, otherwise explain why

Start setup now.
```

### Step 3: During development

1. AI reads your rules before coding
2. After fixing bugs, AI asks if you want to record
3. You say "record" → saved to `LESSONS_LEARNED.md`
4. Universal issues → sync to central rules repo

### Step 4: Periodic sync

Review `LESSONS_LEARNED.md` from your projects and sync universal rules to this repo.

---

## Directory Structure

```
vibe-coding-rules/
├── MASTER_RULES.md              # Core rules (required reading)
├── RULE_QUALITY_CHECKLIST.md    # Quality checklist for rules
│
├── by-category/                 # Rules by problem type
│   ├── time-and-timezone.md
│   ├── error-handling.md
│   ├── user-input.md
│   └── database.md
│
├── by-stack/                    # Rules by tech stack
│   ├── nextjs.md
│   ├── react.md
│   └── supabase.md
│
└── templates/                   # Templates
    ├── SETUP_PROMPT.md          # Setup prompt for new projects
    ├── REVIEW_PROMPT.md         # Rule review prompt
    ├── CLAUDE.md                # Claude Code template
    └── LESSONS_LEARNED.md       # Issue recording template
```

---

## How It Works

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   Project A     │     │   Project B     │     │   Project C     │
│                 │     │                 │     │                 │
│ LESSONS_LEARNED │     │ LESSONS_LEARNED │     │ LESSONS_LEARNED │
└────────┬────────┘     └────────┬────────┘     └────────┬────────┘
         │                       │                       │
         │    Universal rules    │                       │
         └───────────┬───────────┴───────────────────────┘
                     │
                     ▼
         ┌───────────────────────┐
         │  Central Rules Repo   │
         │  (vibe-coding-rules)  │
         │                       │
         │  - by-category/       │
         │  - by-stack/          │
         │  - MASTER_RULES.md    │
         └───────────────────────┘
                     │
                     │  AI reads before coding
                     ▼
         ┌───────────────────────┐
         │     New Project       │
         │                       │
         │  Avoids past mistakes │
         └───────────────────────┘
```

---

## Rule Format

Each rule should include:

```markdown
### [Problem Title]

- **Level**: Required / Strongly Recommended / Suggested
- **Source**: Project name
- **Problem**: What happened
- **Root Cause**: Why it happened
- **Solution**: How to fix
- **Code Example**:
  ```typescript
  // Bad
  ...

  // Good
  ...
  ```
```

---

## Quality Gate

Rules must pass review before syncing:

1. **Universality** - Other projects will face this issue
2. **Quality** - Has code examples and root cause analysis
3. **No Duplicates** - Not already in the rules repo

Use `templates/REVIEW_PROMPT.md` to review rules.

---

## Contributing

1. Fork this repo
2. Add your rules following the format above
3. Submit a PR

---

## License

MIT
