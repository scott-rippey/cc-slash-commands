# Claude Code Slash Commands `v1.3.0`

User-level slash commands for [Claude Code](https://claude.ai/code). Set up once, available in **every project** automatically.

## What This Is

A collection of reusable slash commands that work across all your projects via a single symlink. Edit commands in one place, changes apply everywhere instantly.

## Quick Setup

1. Open your **main development folder** in your IDE (Cursor, VS Code, etc.)

2. Run this in the terminal to clone the repo:
   ```
   git clone https://github.com/scott-rippey/cc-slash-commands.git "slash commands"
   ```

3. Open the new `slash commands/` folder in Claude Code

4. Run `/setup-slash-commands`

That's it. The setup command detects your OS and creates the symlink automatically.

## Included Commands

### Setup

Run once per machine to enable these commands globally.

| Command | Description |
|---------|-------------|
| `/setup-slash-commands` | Create symlink so these commands work in every project |

### Session Tracking

Keep a rolling log of the last 5 sessions in `docs/SESSION_LOG.md`. Use `/log` at the end of a session, `/catchup` at the start of the next one.

| Command | Description |
|---------|-------------|
| `/log` | Log session summary to docs/SESSION_LOG.md |
| `/catchup` | Load recent session history to pick up where you left off |

### Documentation

Checks `CLAUDE.md` in the root and project documentation in `/docs`.

| Command | Description |
|---------|-------------|
| `/audit` | Audit CLAUDE.md and documentation health |

### Git Worktree Workflow

Keep your main branch clean by doing all development in a worktree. Run `/setup-worktree` once per project to create a `dev` worktree, then use `/push` and `/merge` to manage changes.

| Command | Description |
|---------|-------------|
| `/setup-worktree` | Set up git worktree structure for safe development |
| `/push` | Push current work to dev branch |
| `/merge` | Merge dev to main and sync local |
| `/status` | Show git status and current state |
| `/new-feature` | Create a new feature branch worktree |
| `/fix-worktree` | Fix worktree path after syncing between machines |

## How It Works

**What's a symlink?** A symlink (symbolic link) is like a shortcut or alias. Instead of copying files, it points to where the real files live. Claude Code looks for commands in `~/.claude/commands/`, but that folder is just a pointer to this one.

**Why put this in your dev folder?** So you can open it like any other project, edit the `.md` files directly, and even use Claude Code to help you customize commands. This folder is the master copy - edit here, and it works everywhere instantly.

```
Your Dev Folder/
  slash commands/        ← The real files (edit here)
  project-a/
  project-b/

~/.claude/commands/      ← Symlink pointing to "slash commands/"
                           Claude Code reads from here
```

## Customizing

### Edit Existing Commands

Edit any `.md` file in this folder. Changes take effect immediately in all projects.

### Add New Commands

1. Create a new `.md` file (e.g., `my-command.md`)
2. Add frontmatter:
   ```markdown
   ---
   description: What this command does
   ---

   Your prompt instructions here...
   ```
3. Use `/my-command` in any project

### Get Updates

Open the `slash commands/` folder and run `git pull`. New and updated commands are immediately available everywhere.

## Manual Setup

If `/setup-slash-commands` doesn't work for some reason:

**macOS / Linux:**
```bash
mkdir -p ~/.claude
ln -s "/full/path/to/slash commands" ~/.claude/commands
```

**Windows (PowerShell as Admin):**
```powershell
mkdir "$env:USERPROFILE\.claude" -Force
New-Item -ItemType SymbolicLink -Path "$env:USERPROFILE\.claude\commands" -Target "C:\full\path\to\slash commands"
```

## Requirements

- [Claude Code CLI](https://claude.ai/code) installed
- macOS, Linux, or Windows
- Git (standard git commands only - GitHub CLI `gh` is not required)

## Changelog

### v1.3.0
- `/log` now auto-cleans old entries, keeping only the 5 most recent
- `/catchup` simplified to always load last 5 entries

### v1.2.0
- Improved `/setup-worktree` and `/new-feature` with explicit naming instructions and examples

### v1.1.0
- Removed GitHub CLI (`gh`) dependency from `/merge` - uses standard git only

### v1.0.0
- Initial release with core slash commands

## License

MIT - Use these commands however you like.
