---
description: Fix worktree path after syncing to a different machine
---

Fix the git worktree reference for this machine.

This worktree's .git file contains a path from a different machine. Regenerate it:

1. Determine the current absolute path to this worktree folder
2. Determine where the main project folder is (sibling folder without -worktrees suffix)
3. Get the branch name this worktree should be on (probably the folder name)
4. Remove the broken worktree reference: git worktree remove [path] --force (from main repo)
5. Re-add this worktree: git worktree add [this-path] [branch-name]
6. Confirm the worktree is now properly linked

If there are uncommitted changes, warn me before doing anything destructive.
