---
description: Create a new slash command file
---

Help me create a new slash command. Guide me through this step by step.

**Step 1: Ask me for the command name**
- Lowercase, hyphens for spaces (e.g., `review-code`, `deploy-staging`)

**Step 2: Ask me what I want this command to accomplish**
- Let me describe it in plain language
- Ask clarifying questions if my description is vague:
  - What triggers this? What's the starting point?
  - What should Claude do step by step?
  - Should Claude ask me questions or just execute?
  - What does "done" look like?

**Step 3: Structure my idea into an effective Claude Code command**

Apply these principles:
- **Clear task**: What should Claude do when this runs?
- **Sequential steps**: If there's a workflow, number the steps
- **Ask when unsure**: Don't assume - prompt the user for input when needed
- **Define success**: What's the end result? What should Claude confirm?

**Step 4: Write the command file**

Save the `.md` file to `~/.claude/commands/[name].md`. Use the other commands there as reference for format.