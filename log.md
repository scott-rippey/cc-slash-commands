---
description: Log session summary to docs/SESSION_LOG.md (smart - analyzes before writing)
---

Log this session to `docs/SESSION_LOG.md`.

**Before writing, analyze:**

1. Read `docs/SESSION_LOG.md` if it exists
2. Check if there's already an entry for today (## YYYY-MM-DD format)
3. If today's entry exists:
   - Compare what's there vs what we accomplished this session
   - If the new info is substantially different or adds progress, UPDATE the existing entry (don't duplicate)
   - If it's essentially the same, do nothing and tell me "Log already up to date"
4. If no entry for today, create one

**Writing rules:**

- One entry per day maximum
- Format: `## YYYY-MM-DD` followed by 1-3 sentences
- First sentence: what was accomplished
- Second sentence (optional): what's next or blocked
- No bullet points, no code snippets, no verbose explanations
- If updating: KEEP all existing content, then ADD new accomplishments. Never delete or summarize away existing details.

**What NOT to log:**

- Documentation-only changes (CLAUDE.md restructuring, updating docs/, this log itself)
- Typo fixes, formatting cleanup, comment updates
- Refactoring that doesn't change behavior
- Only log if there were actual code/feature/database changes worth noting

**If user provided arguments:**
Use this as the summary: $ARGUMENTS

**If no arguments:**
Analyze our conversation and write a minimal summary focusing on outcomes.

**Format example:**
```markdown
# Session Log

## 2026-01-23
Completed Stripe webhook integration and tested payment flows. Next: Twilio SMS confirmation.

## 2026-01-22
Set up Groundwork AI project structure and database schema. Next: PDF parsing for estimates.
```

**After writing, cleanup old entries:**

- This log is for recent context only, not permanent history
- Keep only the 5 most recent date entries
- If there are more than 5 entries after adding/updating, delete the oldest ones
- The log should never have more than 5 `## YYYY-MM-DD` sections

**After writing:**
Confirm what you did: "Updated today's log" or "Created new entry for today" or "Log already current, no changes needed."