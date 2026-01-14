# Setup Prompt

> Copy and paste this to your AI assistant when starting a new project

---

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

---

## After Setup

The AI will:
1. Read your rules before writing code
2. Ask to record after fixing bugs
3. Review quality before syncing to central repo
