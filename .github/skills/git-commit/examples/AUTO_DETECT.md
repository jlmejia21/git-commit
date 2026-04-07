# Auto-Detection Examples

## File Pattern → Type Mapping

| Changed Files            | Detected Type | Example Message                       |
| ------------------------ | ------------- | ------------------------------------- |
| `README.md`              | `docs`        | `docs: update README`                 |
| `docs/api.md`            | `docs`        | `docs: add API documentation`         |
| `package.json`           | `chore`       | `chore: update dependencies`          |
| `requirements.txt`       | `chore`       | `chore: add Python dependencies`      |
| `src/login.ts`           | `feat`        | `feat(auth): add login functionality` |
| `src/bug-fix.ts`         | `fix`         | `fix: resolve validation error`       |
| `__tests__/auth.test.ts` | `test`        | `test: add auth tests`                |
| `src/styles.css`         | `style`       | `style: format CSS`                   |
| `.github/workflows/`     | `ci`          | `ci: add CI pipeline`                 |
| `Dockerfile`             | `ci`          | `ci: optimize docker build`           |

## Priority When Multiple Types

```
src/new-feature.ts + __tests__/test.ts + docs/README.md
→ Priority: feat > test > docs
→ Type: feat

Result: feat: add new feature module
```

## Custom Detection

Add to skill to customize:

```yaml
auto-detect:
  - pattern: "*.prompt.md"
    type: "prompt"
  - pattern: "*.skill.md"
    type: "skill"
```
