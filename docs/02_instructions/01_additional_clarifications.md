# Additional Clarifications

1. Frontmatter location: where should the cover and structure overview files live?
Answer: Option B: content/00_frontmatter/

Reasoning: The frontmatter files should be placed under the content/00_frontmatter/ folder. This keeps them separate from the main content of the report and ensures clarity in the folder structure. It also maintains consistency with the other sections.

2. Figures and appendices placement: should they be section-based or folder-based?
Answer: Option A: content/figures/figures.qmd and content/appendices/appendices.qmd

Reasoning: Figures and appendices should be placed in dedicated, top-level folders like content/figures/ and content/appendices/. This simplifies the structure and ensures they are easily accessible without being mixed in with specific sections of the report. This also avoids clutter in section folders and keeps everything organized.

3. Is 00_1_structure_overview.qmd required?
Answer: Yes

Expected path: content/00_frontmatter/00_1_structure_overview.qmd
Expected content: This file should provide a high-level overview of the report structure. It should outline what each section of the report covers, giving readers a roadmap of the document. This helps provide clarity at the start of the report and may include sections such as "Introduction," "Literature Review," "Methodology," etc.

4. Which naming source is authoritative when there are mismatches?
Answer: The template filenames are authoritative (e.g., 02_2_definitions.qmd). Any mismatches in naming between templates should align with the established template structure and not the internal references in the content.

For example: Use 02_2_definitions.qmd and not 02_2_churn_definition.qmd or 02_2_definitions.qmd with a different name.
Reasoning: Template filenames should be consistent to avoid confusion when including or linking files within the report structure. Templates are the source of truth for file naming conventions. This ensures that all references in the content align with the actual file names, preventing errors during rendering and maintaining a clear structure.

5. Idempotency behavior on re-run: what should happen by default?
Answer: Skip existing files, fail with message

Reasoning: On a re-run, the script should skip existing files and give a warning message. This avoids overwriting valuable work, like user-generated content in sections, while still indicating the existing files were not overwritten. If the user wants to force the script to overwrite files, they can use a flag.
Force flag: Include a --force flag, but it should only overwrite generated files (e.g., templates) and not user-modified content. This allows users to update the structure without losing their work, while still giving them control over what gets overwritten.

6. Output directory decision: output/ or reports/?
Answer: output/

Reasoning: The folder structure and YAML configuration should use output/ as the designated folder for final rendered reports. This is consistent with Quarto's default behavior, and using output/ separates the final report from the working files, which are usually found in the content/ folder. This also allows for a clear distinction between source files and generated output, making it easier to manage and organize the project.

7. Title substitution spec:
Answer:

- Placeholder token: Use {{title}} as the placeholder for the title.
- Files that require substitution: The title should be substituted in:
  - Cover page (e.g., content/00_frontmatter/cover.qmd)
  - Report metadata (e.g., _quarto.yml)
  - Section headers (e.g., content/section_01/01_0_executive_summary.qmd)
  - README (if required)
- Slug and human-readable title:
  - Slug: Should be stored in the configuration and used for file naming (e.g., real-estate-prediction).
  - Human-readable title: This can be stored separately as part of the metadata in the Quarto config or frontmatter (e.g., "Real Estate Prediction").

8. Should the script run render validation automatically?
Answer: Yes, and failure should cause a non-zero exit

Reasoning: Automatically running a render validation step ensures that the generated report works as expected, without errors. If the validation fails, the script should exit with a non-zero status to prevent incomplete or broken reports from being generated. This allows users to catch issues early and ensures that the final output is of high quality. Additionally, providing clear error messages during validation can help users understand what went wrong and how to fix it.

9. README generation scope:
Answer: Scaffold a minimal README and let users expand it

Reasoning: The script should generate a minimal README.md with the basic project details, file structure, and usage instructions. The user can then expand upon it to fit their specific needs. This approach avoids overwhelming users with a detailed README that may not fit their specific use case. It also allows users to customize the README to better reflect their project and provide additional information as needed.

10. Template extension policy:
Answer: All generated files should be .qmd files. The templates themselves should also be in .qmd format (not .md).

Reasoning: Since the Quarto system uses .qmd files for rendering, all generated files, including templates and any other content files, should adhere to the .qmd format. This ensures that everything is consistent and compatible with Quarto’s processing pipeline.
Additional Note: .md files will not be used in the script. All files, whether they are part of the template or generated content, must be .qmd to work correctly with Quarto.

So, in summary: The script should only generate .qmd files, and all template files must be .qmd as well.