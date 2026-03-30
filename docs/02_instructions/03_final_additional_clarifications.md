# Third set of Additional Clarifications

1. Cover Filename Consistency
Answer: The canonical filename for the cover page should be content/00_frontmatter/00_0_cover.qmd.

Reasoning: The convention for filenames in the frontmatter directory should follow the numbered format (e.g., 00_0_cover.qmd). This ensures consistency with the rest of the structured content and maintains an organized file naming system.

Note: The other version, content/00_frontmatter/cover.qmd, should not be used as the canonical name. The numbered prefix (e.g., 00_0_) is preferred for clarity and consistency across the report.

2. Fast Validation Exact Behavior
Answer: The fast validation mode should run quarto check only.

Reasoning: quarto check will perform a basic check of the project to ensure that all files are in place and the content is structured properly. It doesn't require a full render, making it ideal for fast validation during development.

Note: The fast validation mode should not generate any output (like PDFs) but should check the project's integrity and structure to catch common errors early in the development cycle.

3. Default Validation Mode
Answer: The default validation mode when the user runs the script with no validation flag should be full render validation.

Reasoning: Running a full render validation by default ensures that the entire report, including the PDF, is correctly generated, and the user is immediately informed of any rendering issues (e.g., LaTeX dependencies missing). This provides a more thorough validation by default.

Note: This default behavior ensures that the report is fully validated for production and provides the most comprehensive feedback for the user.

4. Manifest File Location and Lifecycle
Answer: The manifest file should be located at .mkquarto/generated_files_manifest.txt.
Lifecycle:

Update: The manifest should be updated on every run of the script.
File Removal: The script should prune removed files from the manifest on each run to ensure that the manifest only contains paths to currently generated files.

Reasoning: This ensures that the manifest accurately reflects the files the script has generated, and it helps to maintain consistency across different runs of the script. Removing files from the manifest helps prevent orphaned paths from being tracked.

5. References Section Mechanics
Answer: 10_0_references.qmd should contain only a heading and a bibliography directive, not example prose.

Reasoning: The references section should be minimal and focus on the structure required to handle citations and the bibliography correctly. The file should include the appropriate bibliography directive (e.g., bibliography: references.bib) and a clear heading, but example prose or additional content should not be included by default.

Note: Keeping the references section minimal ensures flexibility for users to customize it with their own citations and content while maintaining the necessary structure for Quarto to render the references correctly.

Summary:
1. Cover Filename: Use content/00_frontmatter/00_0_cover.qmd.
2. Fast Validation Behavior: Use quarto check only for fast validation.
3. Default Validation: Default to full render validation unless a specific validation flag is set.
4. Manifest File: Store it at .mkquarto/generated_files_manifest.txt, update on every run, and prune removed files.
5. References Section: Keep 10_0_references.qmd minimal, with just the heading and bibliography directive.

## Superseded Note

The references section behavior above is superseded.

Current canonical rule:
- content/section_10/10_0_references.qmd is generated from the section_10 template source.
- The script must not special-case or hardcode a minimal references section.

See the authoritative specification in docs/02_instructions/04_canonical_spec.md.
