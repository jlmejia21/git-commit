---
name: markdown-to-pptx
description: "Use when: converting markdown outlines to PowerPoint presentations - generates structured PPTX files from markdown content with title, content, and image slides"
---

# Markdown to PPTX Skill

## Overview

This skill converts markdown outlines into professional PowerPoint presentations. It follows a two-step workflow: first generate a structured markdown outline, then convert it to PPTX.

## When to Use This Skill

- Create presentations from a topic or brief
- Generate pitch decks, roadmaps, or product presentations
- Convert documentation or notes into slides
- Need PPTX output for business/professional use

## Workflow

### Step 1: Generate Markdown Outline

Create a structured markdown file with the presentation content:

```markdown
# Presentation Title

## Slide 1: Title Slide
- **Title:** Your Presentation Title
- **Subtitle:** Optional subtitle
- **Author:** Presenter Name

## Slide 2: Agenda
- Introduction
- Main Topic 1
- Main Topic 2
- Conclusion

## Slide 3: Content Slide
- **Point 1:** Description
- **Point 2:** Description
- **Point 3:** Description

## Slide 4: Summary
- Key takeaway 1
- Key takeaway 2
- Call to action
```

### Step 2: Convert to PPTX

Use the `markdown-to-pptx` tool to convert:

```bash
npx markdown-to-pptx --input presentation.md --output presentation.pptx
```

Or with Python:

```bash
python -m pip install markdown-to-pptx
python -m markdown_to_pptx presentation.md presentation.pptx
```

## Markdown Format Rules

### Slide Types

| Syntax              | Slide Type         |
| ------------------- | ------------------ |
| `# Title`           | Presentation title |
| `## Slide N: Title` | Content slide      |
| `###`               | Bullet points      |
| `- **Bold:** text`  | Formatted content  |
| `---`               | Slide separator    |

### Content Guidelines

- Use `## Slide N: Title` for each slide
- Keep bullets concise (max 5-6 per slide)
- Use `--` for speaker notes
- Include image references as `![alt](path)`
- Use tables for data comparisons

## Supported Elements

- ✅ Title slides
- ✅ Content slides with bullets
- ✅ Two-column layouts
- ✅ Images
- ✅ Tables
- ✅ Speaker notes
- ✅ Section dividers

## Example Prompts

```
Create a 10-slide product launch deck from the attached brief.
First generate the markdown outline for approval, then convert to PPTX.
```

```
Convert this meeting notes markdown into a 5-slide executive summary presentation.
```

```
Generate a pitch deck for my SaaS startup.
Include: problem, solution, market size, product, team, ask.
Output as PPTX.
```

## Tools & Dependencies

### Option 1: Node.js

```bash
npm install -g @carbon/markdown-to-pptx
# or
npx markdown-to-pptx-cli
```

### Option 2: Python

```bash
pip install python-pptx
```

### Option 3: Use slides-grab (advanced)

For more control over styling:

```bash
git clone https://github.com/vkehfdl1/slides-grab.git
cd slides-grab
npm ci
npx playwright install chromium
```

## Guardrails

- Always show the markdown outline first for user approval before generating PPTX
- Verify the PPTX file was created successfully
- Provide download/link to the generated file
- Keep slide content concise - max 6 bullets per slide
- Use consistent formatting throughout

## Output

The skill will:

1. Generate a structured markdown outline
2. Request user approval on the outline
3. Convert to PPTX using the selected tool
4. Verify file creation
5. Provide the final file path
