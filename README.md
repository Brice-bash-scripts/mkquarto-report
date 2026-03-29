# mkquarto_report

A Bash-driven scaffolding project for generating a professional, PDF-first Quarto technical report template.

## Overview

This repository defines the requirements and blueprint for a script that creates a reusable Quarto report structure. The focus is on:

- Production-ready report scaffolding
- Clean, repeatable project layout
- PDF-compatible Quarto configuration
- Preloaded section templates that guide report writing

## Project Goals

The intended script should:

- Create a complete Quarto report directory structure
- Generate required core files (`report.qmd`, `_quarto.yml`, `references.bib`)
- Preload structured `.qmd` section templates
- Be idempotent and safe to re-run
- Avoid creating unplanned files/folders
- Work in Linux/WSL environments

## Current Repository Contents

This repository currently contains planning and instruction documents:

```text
docs/
  01_overview/
    md_outline.md
  02_instructions/
    mkquarto_instructions.md
```

## Key Requirements (From Docs)

### 1. Scaffold Structure
Create a `technical_report/` workspace with:

- Root files: `report.qmd`, `_quarto.yml`, `references.bib`
- Content directories and section files under `content/`
- Asset directories (`assets/images`, `assets/tables`)
- Output directory (`output/`)

### 2. Bash Script Quality
The script is expected to be:

- Non-interactive (CI/CD friendly)
- Clear and maintainable
- Status-message driven for usability
- Error-aware (dependency and permission checks)

### 3. Quarto Output Focus
The generated project should support reliable PDF rendering with:

- Quarto config tuned for report output
- Compatible markdown and section structure
- Reference-ready bibliography setup

## Source Documents

- `docs/01_overview/md_outline.md`: high-level specification outline and validation checklist
- `docs/02_instructions/mkquarto_instructions.md`: detailed project structure and implementation expectations

## Suggested Next Steps

1. Implement the scaffold script (for example: `mkquarto_report.sh`) based on the instruction doc.
2. Run the script and verify the generated tree exactly matches the spec.
3. Validate output with Quarto render.
4. Add sample content and confirm PDF build quality.

## Validation Checklist

- Script runs without errors
- All required directories/files are created
- No extra folders/files are introduced
- Script can be re-run safely (idempotent behavior)
- Quarto project renders to PDF successfully

## Status

Planning and specification are complete in `docs/`. Implementation script is the next milestone.