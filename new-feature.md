---
description: Create a new feature branch worktree for parallel work
---

I want to create a new feature branch worktree.

Ask me what to name the feature (keep it short, lowercase, hyphens for spaces).

Then:

1. Create a new branch named feature-[name] based on current dev or main
2. Create a new worktree in ../{{PROJECT_NAME}}-worktrees/{{PROJECT_NAME}}-feature-[name]/ (so it shows the app name in Cursor's workspace)
3. Copy over any .env.example or .env.sample files
4. Tell me the full path to the new worktree

Remind me that when this feature is done, I should:
- Push the feature branch
- Merge to dev (or main) on GitHub
- Delete the worktree with: git worktree remove ../{{PROJECT_NAME}}-worktrees/{{PROJECT_NAME}}-feature-[name]