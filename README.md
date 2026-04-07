# Agent Skills

Colección de skills para agentes de IA coding.

## Skills Disponibles

| Skill                                                | Descripción                                                               |
| ---------------------------------------------------- | ------------------------------------------------------------------------- |
| [git-commit](.github/skills/git-commit/)             | Commits interactivos con auto-detección de tipo y mensajes convencionales |
| [markdown-to-pptx](.github/skills/markdown-to-pptx/) | Convierte esquemas markdown a presentaciones PowerPoint (PPTX)            |
| [readme-generator](.github/skills/readme-generator/) | Genera, actualiza y mejora archivos README.md                             |

## Instalación

```bash
# Instalar todos los skills
npx skills add joseluis/agents-skills

# Instalar un skill específico
npx skills add joseluis/agents-skills --skill git-commit
npx skills add joseluis/agents-skills --skill markdown-to-pptx
npx skills add joseluis/agents-skills --skill readme-generator
```

---

## Uso

### git-commit

Commits interactivos con confirmación antes de ejecutar:

1. **Mostrar status** — `git status` para ver cambios
2. **Auto-detectar tipo** — Analiza archivos modificados
3. **Construir mensaje** — Genera mensaje convencional
4. **Confirmar** — Muestra propuesta antes de ejecutar
5. **Ejecutar** — Solo hace `git add` + `git commit` tras aprobación

**Auto-detección de tipo:**

| Archivos modificados     | Tipo    |
| ------------------------ | ------- |
| `*.md`, `docs/`          | `docs`  |
| `test/*`, `*.test.ts`    | `test`  |
| `package.json`, `*.lock` | `chore` |
| `.github/`               | `ci`    |
| `src/*.ts` (nuevo)       | `feat`  |
| `src/*.ts` (fix)         | `fix`   |
| `*.css`, `*.scss`        | `style` |

**Override manual:**

```bash
/git-commit feat: add new feature
/git-commit fix: resolve bug
```

---

### markdown-to-pptx

Convierte esquemas markdown a presentaciones PowerPoint:

1. **Generar outline** — Crear archivo markdown con estructura
2. **Aprobar** — Mostrar outline para aprobación del usuario
3. **Convertir** — Generar PPTX usando `python-pptx` o `slides-grab`

**Ejemplo de outline:**

```markdown
# Título de Presentación

## Slide 1: Portada
- **Title:** Mi Presentación
- **Subtitle:** Subtítulo

## Slide 2: Contenido
- Punto 1
- Punto 2
```

**Instalación de dependencias:**

```bash
# Python
pip install python-pptx

# Node.js
npm install -g @carbon/markdown-to-pptx
```

---

### readme-generator

Genera, actualiza y mejora archivos README.md:

1. **Analizar proyecto** — Detectar tipo, lenguaje, dependencias
2. **Generar estructura** — Crear README con secciones apropiadas
3. **Revisar** — Verificar que tenga: instalación, uso, API, contribución

**Secciones generadas:**

| Sección      | Descripción                     |
| ------------ | ------------------------------- |
| Title        | Nombre del proyecto             |
| Description  | Resumen de 1-2 oraciones        |
| Features     | Lista de características        |
| Installation | Instrucciones de instalación    |
| Usage        | Ejemplos de uso                 |
| API          | Referencia de funciones/métodos |
| Contributing | Cómo contribuir                 |
| License      | Tipo de licencia                |

---

## Estructura del proyecto

```
agents-skills/
├── README.md
└── .github/
    └── skills/
        ├── git-commit/
        │   └── SKILL.md
        ├── markdown-to-pptx/
        │   └── SKILL.md
        └── readme-generator/
            └── SKILL.md
```

## Contribuir

1. Fork del repositorio
2. Crear skill en `.github/skills/<nombre>/SKILL.md`
3. Push y crear PR

## Ver también

- [Skills CLI](https://github.com/vercel-labs/skills)
- [Directorio de skills](https://skills.sh/)
