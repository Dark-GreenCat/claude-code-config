# claude-code-config

My Claude Code setup: a TokyoNight Storm theme and a status line.

## Files

| Path | What it is |
|------|------------|
| `themes/tokyonight.json` | Custom Claude Code theme based on the dark theme, using Tokyo Night Storm colors. Diff colors come from a reference screenshot. |
| `statusline-command.sh` | Status line script: model and effort, context tokens, folder, git branch, and 5h/7d rate-limit bars. |
| `settings.json` | Claude Code settings that select the custom theme and the status line script. |

## Install

1. Copy the files into `~/.claude/`:

   ```bash
   mkdir -p ~/.claude/themes
   cp themes/tokyonight.json ~/.claude/themes/
   cp statusline-command.sh ~/.claude/
   cp settings.json ~/.claude/settings.json   # or merge the keys you need
   ```

2. Make sure your terminal supports truecolor. Add this to your shell rc file, then open a new shell:

   ```bash
   export COLORTERM=truecolor
   ```

3. Restart Claude Code, or run `/theme` and choose `tokyonight`.

## Requirements

- `jq`, used by the status line script.
- A Nerd Font in your terminal. The folder and branch icons (`U+F07B`, `U+E0A0`) won't render otherwise.

## Notes

- Claude Code's built-in syntax highlighting for code blocks isn't controlled by the theme file, so code blocks keep their default colors.
- The unchanged lines in a diff use the terminal background. The theme file can't set that color.
