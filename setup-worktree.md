---
description: Set up git worktree structure for safe development
---

Set up a git worktree workflow for this project:

1. Create a 'dev' branch if it doesn't exist
2. Create a worktrees folder adjacent to this project (../{{PROJECT_NAME}}-worktrees/)
3. Create a worktree for the dev branch in that folder, named {{PROJECT_NAME}}-dev (so it shows the app name in Cursor's workspace)
4. Copy over any .env.example or .env.sample files (not .env.local) to the worktree
5. Tell me the full path to the new worktree so I can open Claude Code there

My main folder should stay on main as a clean production mirror. All development work will happen in the dev worktree.