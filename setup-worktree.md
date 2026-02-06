---
description: Set up git worktree structure for safe development
---

Set up a git worktree workflow for this project:

1. Get the EXACT name of the current project folder by running `basename "$(git rev-parse --show-toplevel)"` — use this exact output, do NOT rename, normalize, or infer the name from package.json, git remote, or anything else
2. Create a 'dev' branch if it doesn't exist
3. Create a worktrees container folder adjacent to this project using the EXACT same name + `-worktrees` (e.g., `../my-app-worktrees/`)
4. Create a worktree for the dev branch inside that container, using the EXACT same name + `-dev` (e.g., `../my-app-worktrees/my-app-dev/`)
5. Copy over any .env.example or .env.sample files (not .env.local) to the worktree
6. Tell me the full path to the new worktree so I can open Claude Code there

Example structure:
```
Dev/
  my-app/                    <- main folder (stays on main branch)
  my-app-worktrees/          <- container folder
    my-app-dev/              <- dev worktree
```

My main folder should stay on main as a clean production mirror. All development work will happen in the dev worktree.