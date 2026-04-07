# Git Commit Skill Examples

## 1. Automatic Detection

User types:

```
/git-commit
```

Skill output:

```
Detected: .github/skills/ → type: feat (new feature)
Message: feat(skills): add git-commit skill for conventional commits

→ git status
→ git add -A
→ git commit -m "feat(skills): add git-commit skill for conventional commits"
✓ Committed
```

## 2. Direct Message

User types:

```
/git-commit "fix: resolve login redirect bug"
```

Skill output:

```
Message: fix: resolve login redirect bug

→ git add -A
→ git commit -m "fix: resolve login redirect bug"
✓ Committed
```

## 3. Manual Type + Scope

User types:

```
/git-commit --type=refactor --scope=api
```

Skill output:

```
Type: refactor, Scope: api
Description: (prompt user or generate from changes)

→ git commit -m "refactor(api): optimize user queries"
✓ Committed
```

## 4. Specific Files

User types:

```
/git-commit src/auth/
```

Skill output:

```
Files: src/auth/
Detected: src/auth/*.ts → type: feat (new feature)

→ git add src/auth/
→ git commit -m "feat(auth): add authentication module"
✓ Committed
```

## 5. Breaking Change

User types:

```
/git-commit "feat(api)!: change response format"
```

Skill output:

```
Type: feat, Scope: api
Breaking: YES

→ git commit -m "feat(api)!: change response format"

Body (optional):
BREAKING CHANGE: The response format has changed from v1 to v2
✓ Committed with breaking change
```

## 6. With Issue Reference

User types:

```
/git-commit "fix: resolve token expiration" --closes #123
```

Skill output:

```
Message: fix: resolve token expiration
Footer: Closes #123

→ git commit -m "fix: resolve token expiration

Closes #123"
✓ Committed
```
