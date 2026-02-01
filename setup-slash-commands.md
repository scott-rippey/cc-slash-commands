---
description: Set up these slash commands as user-level (run once per machine)
---

Set up this `slash commands/` folder as user-level commands so they work in every project.

**Pre-check:**
- Verify the current working directory is named `slash commands` and contains `.md` command files
- If not, tell the user: "Run this from inside the `slash commands/` folder. It should be placed at the root of your main development folder, alongside all your projects."

**Instructions:**

1. Detect the operating system (macOS, Linux, or Windows)
2. Get the full absolute path to the current working directory (this is the `slash commands/` folder)
3. Check if `~/.claude/commands` already exists:
   - If it's already a symlink pointing here, say "Already set up!" and stop
   - If it's a symlink pointing elsewhere, ask if they want to replace it
   - If it's a real directory with files, warn them and ask before replacing
4. Create the symlink:
   - **macOS/Linux**: `mkdir -p ~/.claude && ln -s "/path/to/slash commands" ~/.claude/commands`
   - **Windows**: `mkdir "$env:USERPROFILE\.claude" -Force` then `New-Item -ItemType SymbolicLink -Path "$env:USERPROFILE\.claude\commands" -Target "C:\path\to\slash commands"`
5. Verify the symlink was created successfully
6. Confirm: "Done! These commands are now available in every project. Try `/log` or `/catchup` in any project."

**Important:**
- On Windows, the terminal may need to run as Administrator to create symlinks
- Use the actual full path to this folder, not a relative path
- The folder name has a space in it ("slash commands") so quote the path
