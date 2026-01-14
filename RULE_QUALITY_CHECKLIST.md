# Rule Quality Checklist

> Use this checklist when reviewing rules before adding to the central repo

---

## Single Rule Quality Check

### Required Fields

- [ ] Has clear problem type tag
- [ ] Has specific problem description (not vague like "had a bug")
- [ ] Has root cause analysis (why it happened)
- [ ] Has code example (wrong vs correct)
- [ ] Has source project noted

### Readability

- [ ] Someone unfamiliar with the original project can understand
- [ ] Problem and solution are logically connected
- [ ] Code example can be directly used
- [ ] No project-specific variable names or business terms (or explained)

### Format Consistency

- [ ] Uses standard Markdown format
- [ ] Tags use defined types (time-handling / database / API etc.)
- [ ] Code examples have language identifier (js/ts/python etc.)

---

## Universality Check

```
Q1: Will this issue ONLY occur in this specific project?
    ├── Yes → Keep in project's LESSONS_LEARNED.md
    └── No  → Continue to Q2

Q2: Is this tightly coupled to specific business logic?
    ├── Yes → Keep in project local
    └── No  → Continue to Q3

Q3: Will other projects using the same tech stack encounter this?
    ├── Yes → Add to by-stack/[tech].md
    └── No  → Continue to Q4

Q4: Is this a universal programming issue?
    ├── Yes → Add to by-category/[type].md or MASTER_RULES.md
    └── No  → Keep in project local
```

---

## Whole Repo Check (Monthly)

### Deduplication

- [ ] No identical rules
- [ ] No highly similar rules with different wording
- [ ] Similar rules merged or differences noted

### Consistency

- [ ] No contradicting rules
- [ ] Similar problems have consistent solutions
- [ ] Terminology is unified

### Organization

- [ ] Rules are in correct category directories
- [ ] No duplicates between by-category and by-stack
- [ ] Cross-category rules have proper references

### Freshness

- [ ] No outdated technical solutions
- [ ] No rules superseded by better approaches
- [ ] Tech versions are current

---

## Review Log

| Date | Reviewer | Issues Found | Resolution |
|------|----------|--------------|------------|
| YYYY-MM-DD | | | |
