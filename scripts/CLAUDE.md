# Scripts — extends root CLAUDE.md

Root rules apply. The following add to or override them.

## Shell scripts
- Always add `set -euo pipefail` as first line
- Never use `sudo` without explaining why
- Prefer Python over bash for anything over 50 lines

## Glob rules
- *.sh — always check shellcheck compliance before finishing