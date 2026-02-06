---
description: Create a new feature branch worktree for parallel work
---

I want to create a new feature branch worktree.

Ask me what to name the feature (keep it short, lowercase, hyphens for spaces).

Then:

1. Get the EXACT base project name by running `basename "$(git rev-parse --show-toplevel)"` to find the main repo folder name — use this exact output, do NOT rename, normalize, or infer the name from package.json, git remote, or anything else. If you're in a worktree (e.g., `my-app-worktrees/my-app-dev`), this command returns the main repo folder name (`my-app`)
2. Create a new branch named `feature-[name]` based on current dev or main
3. Create a new worktree in the existing worktrees container: `../[base-name]-worktrees/[base-name]-feature-[name]/`
4. Copy over any .env.example or .env.sample files
5. Tell me the full path to the new worktree

Example: If base project is `my-app` and feature is `auth`:
```
Dev/
  my-app/                           <- main folder
  my-app-worktrees/
    my-app-dev/                     <- dev worktree
    my-app-feature-auth/            <- new feature worktree
```

Remind me that when this feature is done, I should:
- Push the feature branch
- Merge to dev (or main) on GitHub
- Delete the worktree with: `git worktree remove ../[base-name]-worktrees/[base-name]-feature-[name]`