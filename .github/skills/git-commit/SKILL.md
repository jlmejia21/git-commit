---
name: git-commit
description: "Use when: creating git commits interactively - detects file types, applies conventional commits format, shows proposed message for user confirmation before executing git add → commit"
---

# Git Commit Skill

## Workflow (Interactive)

1. **Show status** — Run `git status` to see current changes
2. **Auto-detect type** — Analyze changed files to determine commit type
3. **Build message** — Construct conventional commit automatically
4. **Show proposal** — Display the proposed commit message for user approval
5. **Execute on approval** — Only run `git add -A` then `git commit -m "<message>"` after user confirms

## Interactive Confirmation

Before executing the commit, the skill will:

1. **Display** the proposed commit message with detected type and reason
2. **Ask** for confirmation before proceeding
3. **Execute** only after user approval

Example:

```
Detected: src/*.ts → type: feat (new feature in source code)
Proposed message: "feat(auth): add login validation"

¿Proceder con el commit? (yes/no)
→ If yes: git add -A && git commit -m "feat(auth): add login validation"
→ If no: Cancel operation
```

## Auto-Detection Rules

| Files Changed                                | Type Detected |
| -------------------------------------------- | ------------- |
| `*.md`, `README*`, `docs/`                   | `docs`        |
| `test/*`, `__tests__/*`, `*.test.ts`         | `test`        |
| `package.json`, `requirements.txt`, `*.lock` | `chore`       |
| `.github/`, `.gitlab-ci.yml`, `Dockerfile`   | `ci`          |
| `src/*.ts`, `src/*.js` (new feature)         | `feat`        |
| `src/*.ts`, `src/*.js` (bug fix)             | `fix`         |
| `*.css`, `*.scss`, `style/*`                 | `style`       |
| `refactor`, `reorganize` in message          | `refactor`    |
| Default                                      | `chore`       |

## Auto-Detection Logic

```
IF files match multiple types:
  → Use highest priority: feat > fix > refactor > style > test > docs > ci > chore

IF no files matched:
  → Default to `chore`
```

## Manual Override

The user can specify type manually:

- `/git-commit feat: add new feature` — Force `feat` type
- `/git-commit fix: resolve bug` — Force `fix` type
- `/git-commit --type=refactor --scope=api` — Explicit type and scope

## Output

The skill will output:

- Detected type and reason
- Constructed commit message
- Git command execution

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

The agent will automatically:

1. Run `git status` to see changes
2. Detect commit type based on file patterns
3. Build a conventional commit message from file names/changes
4. **Show the proposed message for confirmation**
5. Execute `git add -A && git commit -m "<message>"` only after user approval

## Manual Override

- `/git-commit "feat: add new feature"` — Direct message
- `/git-commit --type=fix --scope=auth` — Explicit type/scope
- `/git-commit src/utils/` — Commit specific files

## Tips

- **Imperative mood**: "add feature" not "added feature" or "adding feature"
- **Be specific**: "fix login redirect bug" not "fix bug"
- **Reference issues**: Add `Closes #123` in footer
- **Breaking changes**: Use `feat(api)!: change response format` or add `BREAKING CHANGE:` in body

## Example Prompts

- `/git-commit` — Auto-detect type and commit
- `/git-commit "feat: add user authentication"` — Override with custom message
- `/git-commit --type=fix --scope=auth` — Override type and scope
- `/git-commit src/utils/` — Commit specific folder
