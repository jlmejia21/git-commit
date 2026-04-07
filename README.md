# Agent Skills

Colección de skills para agentes de IA coding.

## Skills Disponibles

| Skill                                            | Descripción                                                               |
| ---------------------------------------------- | ------------------------------------------------------------------------- |
| [git-commit](.github/skills/git-commit/)        | Commits interactivos con auto-detección de tipo y mensajes convencionales |
| [markdown-to-pptx](.github/skills/markdown-to-pptx/) | Convierte esquemas markdown a presentaciones PowerPoint (PPTX)            |

## Instalación

```bash
npx skills add joseluis/agents-skills
```

## Uso

### git-commit

Ejecuta el skill para crear commits interactivos:

1. **Mostrar status** — `git status` para ver cambios
2. **Auto-detectar tipo** — Analiza archivos modificados
3. **Construir mensaje** — Genera mensaje convencional
4. **Confirmar** — Muestra propuesta antes de ejecutar
5. **Ejecutar** — Solo hace `git add` + `git commit` tras aprobación

#### Auto-detección de tipo

| Archivos modificados     | Tipo    |
| ------------------------ | ------- |
| `*.md`, `docs/`          | `docs`  |
| `test/*`, `*.test.ts`    | `test`  |
| `package.json`, `*.lock` | `chore` |
| `.github/`               | `ci`    |
| `src/*.ts` (nuevo)       | `feat`  |
| `src/*.ts` (fix)         | `fix`   |
| `*.css`, `*.scss`        | `style` |

#### Override manual

```bash
/git-commit feat: add new feature
/git-commit fix: resolve bug
```

## Estructura del proyecto

```
agents-skills/
├── README.md
└── .github/
    └── skills/
        └── git-commit/
            └── SKILL.md
```

## Contribuir

1. Fork del repositorio
2. Crear skill en `.github/skills/<nombre>/SKILL.md`
3. Push y crear PR

## Ver también

- [Skills CLI](https://github.com/vercel-labs/skills)
- [Directorio de skills](https://skills.sh/)
