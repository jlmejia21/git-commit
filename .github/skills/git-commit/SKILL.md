---
name: git-commit
description: "Use when: creating a git commit with proper workflow - runs git status, stages changes with git add, and commits with a meaningful message following conventional commits format"
---

# Git Commit Skill

## Workflow

1. **Show status** — Run `git status` to see current changes
2. **Validate type** — Ask user for commit type (feat, fix, docs, style, refactor, test, chore)
3. **Build message** — Construct conventional commit: `type(scope): description`
4. **Stage files** — Run `git add <files>` to stage the desired changes
5. **Commit** — Run `git commit -m "<message>"` with validated message

## Conventional Commits Format

```
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

### Types

| Type       | Description                             |
| ---------- | --------------------------------------- |
| `feat`     | New feature                             |
| `fix`      | Bug fix                                 |
| `docs`     | Documentation only                      |
| `style`    | Code style (formatting, semicolons)     |
| `refactor` | Code change that neither fixes nor adds |
| `test`     | Adding or updating tests                |
| `chore`    | Maintenance, deps, build changes        |
| `perf`     | Performance improvement                 |
| `ci`       | CI configuration changes                |

### Validation Rules

- `type` is required and must be one of the valid types
- `description` is required, max 50 chars, lowercase, no period
- Use imperative mood: "add" not "added" or "adds"
- Scope is optional but recommended
- Breaking changes: start body with `BREAKING CHANGE:`

## Usage

```
/git-commit
```

The agent will:

1. Check what files have been modified
2. Ask which type (feat, fix, etc.)
3. Ask for scope (optional) and description
4. Validate format before committing
5. Execute `git add <files>` then `git commit -m "<message>"`

## Arguments

- `files` (optional): Specific files to commit, e.g., `/git-commit src/index.ts`
- `message` (optional): Commit message, e.g., `/git-commit "fix: resolve auth bug"`

## Tips

- **Imperative mood**: "add feature" not "added feature" or "adding feature"
- **Be specific**: "fix login redirect bug" not "fix bug"
- **Reference issues**: Add `Closes #123` in footer
- **Breaking changes**: Use `feat(api)!: change response format` or add `BREAKING CHANGE:` in body

## Example Prompts

- `/git-commit` — Interactive workflow with type selection
- `/git-commit "feat: add user authentication"` — Direct with message
- `/git-commit "fix(auth): resolve token expiration"` — With scope
- `/git-commit src/utils/` — Commit specific folder
