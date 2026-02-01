# Audit CLAUDE.md and Documentation

Audit the project's Claude Code setup. Read docs first, then check CLAUDE.md, then give recommendations.

## Step 1: Read /docs First

Before anything else, scan `/docs/` and read each markdown file to understand what documentation already exists. For each file, note:
- Filename
- What it covers (read first 50+ lines)
- Key topics/sections

Build a mental map of all available documentation.

## Step 2: Check CLAUDE.md

Read `CLAUDE.md` and report:

**Metrics:**
- Line count (target: <300, ideal: <100)
- Instruction count (target: <50 — Claude Code uses ~50 built-in, LLMs max out around 150-200 total)

**Check for:**
- Does it cover WHAT (stack, structure), WHY (purpose), and HOW (commands)?
- Any content that duplicates what's already in a `/docs/` file?
- Any verbose sections that could be shortened?
- Any task-specific details that aren't universally needed every session?

## Step 3: Build the Quick Reference Table

Generate a table mapping tasks to docs files:

```
| For this task... | Read this file | Notes |
|------------------|----------------|-------|
| Database schema changes | `/docs/database_schema.md` | Primary reference |
| Agent scheduling | `/docs/agentic-features-plan.md` | Cron + Edge Functions |
```

This table can be added to CLAUDE.md so future sessions know where to look.

## Step 4: Output

Report in this format:

```
## Health Check
- Lines: X (target <300)
- Instructions: ~Y (target <50)
- [any issues found]

## Docs Index
[the table from Step 3]

## Suggestions
[numbered list — be specific, reference line numbers]
```

## Rules

- **Do NOT edit any files automatically.** Only report findings and suggestions.
- If you think content should move from CLAUDE.md to a docs file, **ask first** and suggest which existing docs file it belongs in (or if a new one is needed).
- Keep output concise. This is a health check, not a rewrite.
- Reference specific line numbers in CLAUDE.md and exact filenames in /docs.