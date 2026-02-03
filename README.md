# Claude Code Slash Commands `v1.1.0`

User-level slash commands for [Claude Code](https://claude.ai/code). Set up once, available in **every project** automatically.

## What This Is

A collection of reusable slash commands that work across all your projects via a single symlink. Edit commands in one place, changes apply everywhere instantly.

## Quick Setup

1. Clone this repo into your **main development folder** (where all your projects live):
   ```bash
   cd ~/Development  # or wherever you keep your projects
   git clone https://github.com/scott-rippey/cc-slash-commands.git "slash commands"
   ```

2. Open the `slash commands/` folder in Claude Code

3. Run `/setup-slash-commands`

That's it. The setup command detects your OS and creates the symlink automatically.

```
Your Dev Folder/
  slash commands/    ← Cloned here, alongside your projects
  project-a/
  project-b/
  project-c/
```

## Included Commands

| Command | Description |
|---------|-------------|
| `/setup-slash-commands` | **Run first!** Set up these commands as user-level |
| `/log` | Log session summary to docs/SESSION_LOG.md |
| `/catchup` | Load recent session history to pick up where you left off |
| `/audit` | Audit CLAUDE.md and documentation health |
| `/status` | Show git status and current state |
| `/push` | Push current work to dev branch |
| `/merge` | Merge dev to main and sync local |
| `/new-feature` | Create a new feature branch worktree |
| `/setup-worktree` | Set up git worktree structure for safe development |
| `/fix-worktree` | Fix worktree path after syncing to a different machine |

## How It Works

```
This folder (slash commands/)
        ↓ symlink
~/.claude/commands/
        ↓ Claude Code reads from here
Available in every project
```

- **This folder**: Contains the actual `.md` command files
- **~/.claude/commands**: Symlink pointing to this folder
- **Claude Code**: Reads commands from ~/.claude/commands
- **Result**: Edit commands here, instantly works in every project

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

```bash
cd "slash commands"
git pull
```

New and updated commands are immediately available everywhere.

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

### v1.1.0
- Removed GitHub CLI (`gh`) dependency from `/merge` - uses standard git only

### v1.0.0
- Initial release with core slash commands

## License

MIT - Use these commands however you like.
