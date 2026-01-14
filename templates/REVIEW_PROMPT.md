# Review Prompt

> Use this to review rules before adding to central repo

---

```
Review this rule for my central rules repo:

[PASTE RULE HERE]

---

Check these criteria:

1. **Universality** (must pass)
   - Will this ONLY happen in this specific project? → Reject
   - Tightly coupled to business logic? → Reject
   - Other projects likely to face this? → Pass

2. **Quality** (must pass)
   - Has code examples (wrong vs correct)?
   - Has root cause analysis?
   - Can someone unfamiliar understand it?

3. **Duplicates**
   - Read my rules repo and check for similar existing rules

Output:
- PASS - Add to [specific file path]
- NEEDS EDIT - [specific suggestions]
- REJECT - [reason: not universal / low quality / duplicate exists]
```
