# claude-dev-kit

This repo is to learn claude code and to understand the hierarchy of claude.md files across folders and to see how claude refines intructions based on the place where the code exists

## Commit format
type(scope): description
Types: feat, fix, chore, docs, refactor, test

## Branch naming
feature/, fix/, chore/

## Always
- Run tests before suggesting changes
- Prefer explicit error handling over silent failures
- Ask before making changes across multiple files

## Never
- Delete files without confirmation
- Modify .env files
- Hardcode secrets or credentials
- warn me on hardcoded variables