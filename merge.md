---
description: Merge dev to main and sync local
---

Merge dev to main and sync everything:

1. Push any uncommitted changes to dev first
2. Merge dev into main using git commands (checkout main, merge dev, push)
3. Find the main project folder (the sibling folder without -worktrees suffix)
4. Pull main to that local main folder
5. Return to this worktree directory
6. Confirm the merge was successful and that local main is now up to date

Do not delete the dev worktree - I'll continue using it for future work.
