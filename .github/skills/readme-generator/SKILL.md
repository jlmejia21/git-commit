---
name: readme-generator
description: "Use when: generating, updating, or improving README files - creates well-structured documentation from project context with sections for installation, usage, and contribution"
---

# README Generator Skill

## Overview

This skill helps generate, update, and improve README.md files for projects. It creates professional documentation following best practices.

## When to Use This Skill

- Create a new README from scratch
- Update existing documentation
- Improve unclear or outdated READMEs
- Add missing sections (installation, usage, etc.)
- Standardize documentation format

## Workflow

### Step 1: Analyze Project

Gather information about the project:

1. **Project type** — library, CLI, web app, etc.
2. **Language/Framework** — Python, Node.js, React, etc.
3. **Key features** — main capabilities
4. **Dependencies** — requires Node.js, Python, etc.
5. **Target audience** — developers, end users, etc.

### Step 2: Generate Structure

Create a well-structured README:

```markdown
# Project Name

Short description (1-2 sentences)

## Features

- Feature 1
- Feature 2
- Feature 3

## Installation

\`\`\`bash
npm install project-name
\`\`\`

## Usage

\`\`\`javascript
import { function } from 'project-name'
\`\`\`

## API

### functionName(options)

| Parameter | Type | Description |
|-----------|------|-------------|
| param1 | string | Description |

## Contributing

See CONTRIBUTING.md

## License

MIT
```

### Step 3: Review & Improve

Check for:

- ✅ Clear title and description
- ✅ Installation instructions
- ✅ Usage examples
- ✅ API reference (if applicable)
- ✅ Contributing guidelines
- ✅ License
- ✅ Badges (optional)

## README Sections

### Required

| Section      | Description          |
| ------------ | -------------------- |
| Title        | Project name         |
| Description  | 1-2 sentence summary |
| Installation | How to install       |
| Usage        | Basic example        |

### Recommended

| Section      | Description               |
| ------------ | ------------------------- |
| Features     | List of key features      |
| API          | Function/method reference |
| Contributing | How to contribute         |
| License      | License type              |

### Optional

| Section   | Description            |
| --------- | ---------------------- |
| Badges    | Build status, version  |
| Demo      | Screenshots, live link |
| Changelog | Version history        |
| FAQ       | Frequently asked       |

## Best Practices

- Keep it concise — max 2-3 sentences for description
- Use code blocks with language tags
- Include working examples
- Link to relevant documentation
- Use badges for CI/CD status
- Add table of contents for long READMEs

## Example Prompts

```
Generate a README for my Node.js CLI tool.
It takes a config file and outputs processed data.
```

```
Improve this README - it's too long and unclear.
Focus on adding better examples.
```

```
Add API documentation to my Python library README.
Functions: parse(), transform(), validate()
```

## Output

The skill will:

1. Analyze project structure and context
2. Generate or update README.md
3. Show the result for approval
4. Save the file to project root
