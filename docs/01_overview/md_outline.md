# Quarto Project Scaffolding Specification

1. Objective
2. Project Structure Requirements
3. Bash Script Requirements
4. Quarto Configuration (_quarto.yml)
5. Preloaded QMD Templates
6. Styling and Formatting Standards
7. Build & Render Requirements
8. Constraints & Rules
9. Expected Output

>🔍 What goes in each section (the part that actually matters)

---

## 1. Objective

Tell the AI what this is building, not how.
Example intent:

- Professional technical report scaffold
- PDF-first (this matters a LOT)
- Reusable template
- Clean, production-ready structure

---

## 2. Project Structure Requirements

Define folders explicitly:

```plaintext
technical_report/
├── report.qmd
├── _quarto.yml
├── references.bib
├── content/
│   ├── 00_frontmatter/
│   ├── section_01/
│   ├── section_02/
│   └── appendices/
├── assets/
│   ├── images/
│   └── tables/
└── output/
```

---

## 3. Bash Script Requirements

>This is where most people get sloppy. Don’t.

Specify:

- OS target (Linux / WSL)
- Idempotency (no duplicate overwrites unless forced)
- Directory creation
- File generation
- Echo status messages (professional touch)

Example constraints:

- Use `mkdir -p`
- Use `cat <<EOF` for file creation
- No interactive prompts

---

## 4. Quarto Configuration (_quarto.yml)

Define EXACTLY what you want:

- PDF output
- TOC behavior
- section numbering
- citation handling

This is where your previous pain lives. Document it.

---

## 5. Preloaded QMD Templates (🔥 most important section)

This is your secret weapon.

Each .qmd should include:

Section header
Instructions to the user
Placeholder text

Example:

### Executive Summary

<!-- 
INSTRUCTIONS:
- Summarize key findings
- 3–5 bullet points
- No technical jargon
-->

[Insert content here]

- You’re not just scaffolding files.
- You’re scaffolding thinking.

---

## 6. Styling and Formatting Standards

Lock this down early or regret it later:

- No inline markdown hacks that break PDF
- Use LaTeX blocks where needed
- Consistent heading hierarchy
- Citation format

---

## 7. Build & Render Requirements

Tell the AI:

- Must support quarto render report.qmd
- Must produce PDF successfully
- No broken references
- No missing resource paths

---

## 8. Constraints & Rules

This is where you prevent your AI assistant from getting “creative”:

- Do NOT introduce additional folders
- Do NOT modify structure
- Do NOT use unsupported markdown features
- Must be compatible with PDF rendering

Basically:

>“Stay in your lane, robot.”

---

## 9. Expected Output

Be explicit:

- Single bash script
- Fully runnable
- No placeholders in script itself
- Clean, readable, production-quality

⚡ Pro Tip (this is what separates you from everyone else)

Add this at the end of the markdown:

### Validation Checklist

The generated script must:

- Run without errors
- Create all required files
- Produce a valid Quarto PDF build
- Include all template instructions
- Follow the specified project structure
- Adhere to styling and formatting standards
- Be idempotent (can be run multiple times without issues)
- Not introduce any additional folders or files
- Be compatible with PDF rendering (no unsupported markdown features)
