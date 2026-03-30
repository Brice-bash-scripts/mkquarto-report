# Mkquarto_report Instructions

## 1. Objective
The goal of this project is to create a professional technical report scaffold using Quarto, with a focus on PDF-first output. The template should be reusable, clean, and production-ready, providing a solid foundation for technical documentation.

## 2. Project Structure Requirements
The project should follow a specific folder structure to ensure organization and clarity:
```plaintext
technical_report/
├── report.qmd
├── _quarto.yml
├── references.bib
├── README.md
├── content/
│   ├── 00_frontmatter/
│   ├── section_01/
│   │   ├── 01_0_executive_summary.qmd
│   │   ├── 01_1_purpose_of_study.qmd
│   │   ├── 01_2_key_findings.qmd
│   │   └── 01_3_recommendations.qmd
│   ├── section_02/
│   │   ├── 02_0_introduction.qmd
│   │   ├── 02_1_background.qmd
│   │   ├── 02_2_definitions.qmd
│   │   ├── 02_3_objectives.qmd
│   │   ├── 02_4_scope.qmd
│   │   └── 02_5_report_structure.qmd
│   ├── section_03/
│   │   ├── 03_0_literature_review.qmd
│   │   ├── 03_1_industry_analysis.qmd
│   │   ├── 03_2_key_drivers.qmd
│   │   ├── 03_3_ml_approaches.qmd
│   │   └── 03_4_gaps_justification.qmd
│   ├── section_04/
│   │   ├── 04_0_data_description.qmd
│   │   ├── 04_1_data_overview.qmd
│   │   ├── 04_2_feature_description.qmd
│   │   ├── 04_3_data_quality.qmd
│   │   └── 04_4_data_preprocessing.qmd
│   ├── section_05/
│   │   ├── 05_0_eda.qmd
│   │   ├── 05_1_univariate_analysis.qmd
│   │   ├── 05_2_bivariate_analysis.qmd
│   │   ├── 05_3_multivariate_analysis.qmd
│   │   ├── 05_4_correlation_analysis.qmd
│   │   └── 05_5_eda_summary.qmd
│   ├── section_06/
│   │   ├── 06_0_methodology_model.qmd
│   │   ├── 06_1_approach_methodology.qmd
│   │   ├── 06_2_algorithms_selection.qmd
│   │   ├── 06_3_evaluate_metrics.qmd
│   │   ├── 06_4_hyperparameter_tuning.qmd
│   │   ├── 06_5_cross_validation.qmd
│   │   ├── 06_6_tools_libraries.qmd
│   │   └── 06_7_methodology_summary.qmd
│   ├── section_07/
│   │   ├── 07_0_results_evaluation.qmd
│   │   ├── 07_1_model_performance_comparison.qmd
│   │   ├── 07_2_confusion_matrix.qmd
│   │   ├── 07_3_visualizations.qmd
│   │   ├── 07_4_feature_importance.qmd
│   │   └── 07_5_results_summary.qmd
│   ├── section_08/
│   │   ├── 08_0_discussion.qmd
│   │   ├── 08_1_interpretation_results.qmd
│   │   ├── 08_2_connect_literature.qmd
│   │   ├── 08_3_limitations.qmd
│   │   └── 08_4_discussion_summary.qmd
│   ├── section_09/
│   │   ├── 09_0_conclusions_recommendations.qmd
│   │   ├── 09_1_conclusions.qmd
│   │   ├── 09_2_recommendations.qmd
│   │   └── 09_3_future_work.qmd
│   ├── section_10/
│   │   └── 10_0_references.qmd
│   ├── figures/
│   │   └── figures.qmd
│   └── appendices/
│       └── appendices.qmd
├── assets/
│   ├── images/
│   └── tables/
└── output/
```

## 3. Bash Script Requirements
The bash script should be designed with the following specifications:
- Target OS: Linux / WSL
- Idempotency: The script should be able to run multiple times without causing issues or creating duplicate files unless explicitly forced.
- Dependency Checks: The script should include dependency checks at the start to ensure that Quarto and other required tools (e.g., LaTeX for PDF rendering) are installed. Additionally, ensure that the script handles permission issues gracefully.
- Directory Creation: The script should create all necessary directories if they do not already exist.
- File Generation: The script should generate all required files, including the main report.qmd, _quarto.yml, and references.bib, as well as the structured content files within the content folder.
- The script should not introduce any additional folders or files beyond what is specified in the project structure.
- The script should ensure compatibility with PDF rendering, avoiding any unsupported markdown features that could cause build failures.
- The script should include error handling to manage potential issues during execution, such as missing dependencies or permission errors.
- The script should provide clear output messages to indicate the progress of the project scaffolding process and any issues encountered.
- The script should Include verbose logging within the script to give users a better understanding of its progress.
- The script should be well-documented with comments explaining each step for maintainability and clarity.
- The script should be designed to be easily customizable for different project needs while adhering to the core structure and requirements outlined above.
- The script should be efficient and optimized for performance, minimizing unnecessary operations and ensuring a smooth user experience.
- The script should be compatible with common shell environments and should not rely on any non-standard utilities or features that may not be available in all environments.
- The script should include a help option to provide users with information on how to use it and what it does.
- The script should be tested to ensure it works as intended and does not produce any unintended side effects when run multiple times or in different environments.
- The script should be designed to be easily extendable in the future, allowing for additional features or modifications without requiring a complete rewrite.
- The script should not require any user input during execution, making it suitable for automated workflows and CI/CD pipelines.
- The script should be designed to be secure, avoiding any potential vulnerabilities or risks associated with file creation and execution.
- The script should be compatible with the latest versions of Quarto and any dependencies required for building the PDF output, ensuring that it remains functional as software updates are released.

## 3.1 Running the Script to Generate the Project
To create a new report using the `mkquarto_report` script, simply run the following command:
```bash
mkquarto_report Real-Estate-Prediction
```
This command will trigger the creation of a new report scaffold using "Real-Estate-Prediction" as the project name. The script will automatically replace placeholders for the report title with "Real Estate Prediction" in the relevant sections, such as the title page, metadata, and config files.

What Happens:
- The script generates a folder structure with all required files and directories.
- It creates the main report.qmd file, along with the necessary sections in the content/ folder.
- All instances where the report title is required (e.g., cover page, table of contents) will use "Real Estate Prediction" automatically.
- The configuration files (like _quarto.yml) will also be updated with the title "Real Estate Prediction."

Customizing the Title:

If you want to customize the report title, simply modify the first argument passed to the script. For example:
```bash
mkquarto_report Mortgage-Analytics
```
- This will generate the report scaffold with the title "Mortgage Analytics" instead.
- This way, the user will clearly understand the process of creating a report, how the script dynamically replaces the title, and how they can easily customize it for future projects.


## 4. Quarto Configuration (_quarto.yml)
The _quarto.yml file should be configured to support PDF output and include any necessary settings for the project. This may include specifying the output format, setting up references, and defining any custom styles or templates that should be used in the report. The configuration should be designed to ensure that the generated PDF is professional and adheres to the formatting standards outlined in the project requirements. The configuration should also be flexible enough to allow for future modifications or additions as needed, while maintaining compatibility with the overall project structure and requirements. The _quarto.yml file should be well-documented with comments explaining each setting and its purpose, making it easier for users to understand and modify as needed. The configuration should also be tested to ensure that it works correctly and produces the desired output when the report is built and rendered. The _quarto.yml file should be included in the project scaffolding process, ensuring that it is generated correctly and placed in the appropriate location within the project structure. The configuration should be designed to be easily maintainable and should follow best practices for Quarto configuration, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future.

- add custom styles or templates to the YAML for consistency in branding or document presentation.
- Ensure that the bibliography is correctly linked to the references.bib file, and explain the proper formatting for citations.
- Example _quarto.yml configuration (adjust as needed for specific project requirements):
```yaml
project:
  output-dir: reports
  render:
    - report.qmd

bibliography: references.bib

format:
  html:
    toc: true
    number-sections: false
  pdf:
    documentclass: article
    top-level-division: section
    toc: false
    number-sections: false
    margin-left: 30mm
    margin-right: 30mm

execute:
  enabled: false
```

## 4.1 README.md
The README.md file should provide clear instructions on how to use the generated project, including how to build and render the report, as well as any necessary prerequisites or setup steps. The README should also include an overview of the project structure, a description of the included templates, and any relevant information about the project requirements and constraints. The README should be well-organized and easy to navigate, providing users with a clear understanding of how to work with the generated project and create their own professional technical reports using Quarto. The README should also include troubleshooting guidance for common issues that may arise during the build and render process, ensuring that users can successfully generate their reports even if they encounter challenges along the way. The README should be included in the project scaffolding process, ensuring that it is generated correctly and placed in the appropriate location within the project structure, providing users with a comprehensive guide to using the generated project effectively and efficiently to create high-quality PDF reports with Quarto. The README should be designed to be easily maintainable and should follow best practices for documentation, ensuring that it remains relevant and useful as the project evolves and as new features or requirements are added in the future. The README should also be designed to be easily customizable, allowing users to modify the content and structure as needed to suit their specific needs and preferences while still adhering to the core requirements and guidelines outlined in the project specifications. The README should be tested to ensure that it provides clear and accurate instructions, and that it effectively guides users through the process of building and rendering their reports using the generated project, while also providing a comprehensive overview of the project structure, templates, and requirements to help users understand how to work with the project effectively and efficiently to create professional technical reports using Quarto.

- Provide a troubleshooting section that addresses common build errors users might encounter (e.g., missing dependencies, errors in LaTeX rendering).
- Within the troubleshooting section include Common Errors: List some common errors users might encounter (e.g., LaTeX errors during PDF rendering, missing files) and provide steps for resolving them.
- Within the troubleshooting section include Testing Workflow: Suggest a testing workflow for users to validate their reports during development. For instance, users could test smaller sections of the report before running the full render to make debugging easier.
- Include a section for troubleshooting section is important and should include a broader range of issues users might encounter, such as problems with paths or missing files.
- include a section on how to customize the project structure or templates for different types of reports or specific use cases, while still adhering to the core requirements and guidelines outlined in the project specifications. This can help users understand how to adapt the generated project to their specific needs while still maintaining a professional and consistent output when building and rendering their reports using Quarto.
- Include a section for the `references.bib` file, explaining how the section files should be included, as this is key for users to understand the structure and relationships between files.
- Within the `references.bib` section, provide clear instructions on how to format references correctly, ensuring that users can easily understand how to add their sources and ensure that they are properly cited in the final report. This can help users manage their references effectively and ensure that they are properly cited in the final output, contributing to the overall professionalism and quality of the generated PDF report using Quarto.
- Also within the `references.bib` section, include instructions on how to handle multiple authors or multiple sources in a single citation.
- Include a section on how to customize the bibliography style or citation format, allowing users to adapt the generated project to different citation standards or preferences while still ensuring that the references are properly linked and rendered in the final PDF output when building and rendering their reports using Quarto. This can help users create professional technical reports that adhere to specific citation requirements or standards while still maintaining a consistent and polished appearance in the final output.
- Include a section for Quarto Customizations: Describe the key settings in the _quarto.yml file, such as how to adjust the layout, styling, or document settings like toc (table of contents) and number-sections. This can help users understand how to customize the Quarto configuration to suit their specific needs while still ensuring that the generated PDF output is professional and adheres to the formatting standards outlined in the project requirements. Providing clear instructions on how to modify the _quarto.yml file can empower users to create reports that are tailored to their specific requirements while still maintaining a consistent and polished appearance in the final output when building and rendering their reports using Quarto.

### example README.md content (ensure to customize based on specific project requirements):
```markdown
# Quarto Technical Report - PDF Generation Instructions
This document provides instructions for generating the Technical Report as a PDF using Quarto.

---

## 1. Cover Page Setup

The cover page is implemented as a separate content file:

technical_report/content/cover.qmd

### Requirements:
- The cover page should contain:
  - Report title
  - Subtitle
  - Student information table
  - Declaration of originality
- The cover page should end with:

\newpage

This ensures the rest of the report begins on a new page.

### Inclusion in Report

The cover page must be included at the top of index.qmd using the include directive.

---

## 2. Rendering the PDF

### Step 1: Ensure Quarto is Installed

Verify installation:

quarto --version

---

### Step 2: Install TinyTeX (One-Time Setup)

quarto install tinytex

This provides the LaTeX engine required for PDF generation.

---

### Step 3: Render the Report

From the technical_report directory:

quarto render report.qmd --to pdf

---

## 3. Output Location

The generated PDF will be saved to:

technical_report/reports/

---

## 4. Notes

- Use \newpage only where a full page break is required (e.g., after the cover page).
- Subsections will not automatically create new pages.
- Ensure all include paths are correct relative to index.qmd.

---

## 5. Troubleshooting

HTML instead of PDF:
- Ensure TinyTeX is installed
- Ensure the --to pdf flag is used

LaTeX errors:
- Re-run: quarto install tinytex

File not found errors:
- Confirm include paths are correct

---

End of instructions.
```

## 4.2 references.bib
The references.bib file should be included in the project scaffolding process and should be properly linked in the _quarto.yml configuration to ensure that citations are handled correctly in the generated report. The references.bib file should be designed to be easily maintainable, allowing users to add, modify, or remove references as needed while still adhering to the proper formatting for BibTeX entries. The file should include clear instructions on how to format references correctly, ensuring that users can easily understand how to add their sources and ensure that they are properly cited in the final report. The references.bib file should be tested to ensure that it works correctly with the Quarto configuration and that citations are properly rendered in the final PDF output, providing a seamless experience for users when managing their references and citations in their reports using Quarto. The references.bib file should be an integral part of the project, ensuring that users have a clear and efficient way to manage their references and citations when creating professional technical reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the proper formatting for BibTeX entries, making it easier for users to manage their references effectively and ensure that they are properly cited in the final report, ultimately contributing to the overall professionalism and quality of the generated PDF output. The references.bib file should also be designed to be flexible and adaptable to different types of sources and citation styles, allowing users to easily manage their references regardless of the specific requirements or preferences they may have for their reports, while still ensuring that the file is properly linked and configured in the Quarto project to ensure that citations are handled correctly in the final output. The references.bib file should be included in the project scaffolding process, ensuring that it is generated correctly and placed in the appropriate location within the project structure, providing users with a clear and efficient way to manage their references and citations when creating professional technical reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the proper formatting for BibTeX entries, making it easier for users to manage their references effectively and ensure that they are properly cited in the final report, ultimately contributing to the overall professionalism and quality of the generated PDF output. The references.bib file should also be regularly reviewed and updated as needed to ensure that it remains relevant and effective in helping users manage their references and citations when creating professional technical reports using Quarto, while also adapting to any changes or updates in citation styles or requirements that may arise over time, ensuring that users can continue to effectively manage their references and citations in their reports using Quarto regardless of any changes or updates in citation standards or practices that may occur in the future.

- Example references.bib entry:
```bibtex
@article{smith2020example,
  title={An Example Article},
  author={Smith, John and Doe, Jane},
  journal={Journal of Examples},
  volume={10},
  number={2},
  pages={123-456},
  year={2020},
  publisher={Example Publisher}
}

@misc{blastchar_telco_churn,
  author       = {blastchar},
  title        = {Telco Customer Churn Dataset},
  year         = {n.d.},
  howpublished = {\url{https://www.kaggle.com/datasets/blastchar/telco-customer-churn}},
  note         = {Kaggle dataset, accessed 2026-02-22}
}

@book{james2021data,
  title={Data Science for Business},
  author={James, Foster and Witten, Daniela and Hastie, Trevor and Tibshirani, Robert},
  year={2021},
  publisher={O'Reilly Media}
}

@conference{doe2022machine,
  title={Machine Learning in Practice},
  author={Doe, Jane and Smith, John},
  booktitle={Proceedings of the International Conference on Machine Learning},
  pages={789-1011},
  year={2022},
  organization={ICML}
}

@website{r2024quarto,
  author       = {RStudio},
  title        = {Quarto Documentation},
  year         = {2024},
  howpublished = {\url{https://quarto.org/docs/}},
  note         = {Accessed 2024-06-01}
}
```

## 4.3 report.qmd
The report.qmd file should serve as the main entry point for the Quarto project, containing the necessary front matter and structure to build and render the PDF report. The file should include clear instructions on how to include the various content sections using the include directive, ensuring that the structure of the report is organized and follows the specified hierarchy. The report.qmd file should also be designed to be easily maintainable, allowing users to modify the structure and content as needed while still adhering to the overall formatting and style guidelines outlined in the project requirements. The file should be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto. The report.qmd file should be included in the project scaffolding process, ensuring that it is generated correctly and placed in the appropriate location within the project structure, providing users with a clear and efficient way to create their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also include any necessary metadata or front matter to ensure that it is properly recognized and rendered by Quarto when the report is built, while also providing clear instructions on how to structure the content and include the various sections of the report effectively, ensuring that users can easily create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications. The report.qmd file should also be designed to be flexible and adaptable to different types of content and presentation styles, allowing users to easily create reports on a wide range of topics while still maintaining a consistent and professional appearance throughout the final output, while also ensuring that the file is properly linked and configured in the Quarto project to ensure that it builds and renders successfully without any issues or errors, providing a seamless experience for users when creating their reports using Quarto. The report.qmd file should be an integral part of the project, serving as the main entry point for building and rendering the PDF report using Quarto, while also providing a clear and efficient way for users to structure their content and include the various sections of their reports effectively, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The report.qmd file should also be regularly reviewed and updated as needed to ensure that it remains relevant and effective in guiding users towards creating high-quality reports using Quarto, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the structure or requirements of the report.qmd file over time, ensuring that users can continue to create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications, while also providing a seamless experience when building and rendering their reports using Quarto. The report.qmd file should also include any necessary instructions or guidance on how to structure the content effectively, ensuring that users can easily create reports that are well-organized and adhere to the specified formatting and style guidelines outlined in the project requirements, while also providing clear instructions on how to include the various sections of the report using the include directive, ensuring that users can easily structure their content and create professional technical reports using Quarto with a clear and organized structure that meets the expectations of stakeholders or publication standards. The report.qmd file should be designed to be easily maintainable and should follow best practices for Quarto document structure, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future, while also providing a clear and efficient way for users to create their reports using Quarto, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also include any necessary metadata or front matter to ensure that it is properly recognized and rendered by Quarto when the report is built, while also providing clear instructions on how to structure the content and include the various sections of the report effectively, ensuring that users can easily create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications. The report.qmd file should be an integral part of the project, serving as the main entry point for building and rendering the PDF report using Quarto, while also providing a clear and efficient way for users to structure their content and include the various sections of their reports effectively, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The report.qmd file should also be regularly reviewed and updated as needed to ensure that it remains relevant and effective in guiding users towards creating high-quality reports using Quarto, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the structure or requirements of the report.qmd file over time, ensuring that users can continue to create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications, while also providing a seamless experience when building and rendering their reports using Quarto. The report.qmd file should also include any necessary instructions or guidance on how to structure the content effectively, ensuring that users can easily create reports that are well-organized and adhere to the specified formatting and style guidelines outlined in the project requirements, while also providing clear instructions on how to include the various sections of the report using the include directive, ensuring that users can easily structure their content and create professional technical reports using Quarto with a clear and organized structure that meets the expectations of stakeholders or publication standards. The report.qmd file should be designed to be easily maintainable and should follow best practices for Quarto document structure, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future, while also providing a clear and efficient way for users to create their reports using Quarto, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also include any necessary metadata or front matter to ensure that it is properly recognized and rendered by Quarto when the report is built, while also providing clear instructions on how to structure the content and include the various sections of the report effectively, ensuring that users can easily create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications. The report.qmd file should be an integral part of the project, serving as the main entry point for building and rendering the PDF report using Quarto, while also providing a clear and efficient way for users to structure their content and include the various sections of their reports effectively, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The report.qmd file should also be regularly reviewed and updated as needed to ensure that it remains relevant and effective in guiding users towards creating high-quality reports using Quarto, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the structure or requirements of the report.qmd file over time, ensuring that users can continue to create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications, while also providing a seamless experience when building and rendering their reports using Quarto. The report.qmd file should also include any necessary instructions or guidance on how to structure the content effectively, ensuring that users can easily create reports that are well-organized and adhere to the specified formatting and style guidelines outlined in the project requirements, while also providing clear instructions on how to include the various sections of the report using the include directive, ensuring that users can easily structure their content and create professional technical reports using Quarto with a clear and organized structure that meets the expectations of stakeholders or publication standards. The report.qmd file should be designed to be easily maintainable and should follow best practices for Quarto document structure, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future, while also providing a clear and efficient way for users to create their reports using Quarto, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also include any necessary metadata or front matter to ensure that it is properly recognized and rendered by Quarto when the report is built, while also providing clear instructions on how to structure the content and include the various sections of the report effectively, ensuring that users can easily create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications. The report.qmd file should be an integral part of the project, serving as the main entry point for building and rendering the PDF report using Quarto, while also providing a clear and efficient way for users to structure their content and include the various sections of their reports effectively, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The report.qmd file should also be regularly reviewed and updated as needed to ensure that it remains relevant and effective in guiding users towards creating high-quality reports using Quarto, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the structure or requirements of the report.qmd file over time, ensuring that users can continue to create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications, while also providing a seamless experience when building and rendering their reports using Quarto. The report.qmd file should also include any necessary instructions or guidance on how to structure the content effectively, ensuring that users can easily create reports that are well-organized and adhere to the specified formatting and style guidelines outlined in the project requirements, while also providing clear instructions on how to include the various sections of the report using the include directive, ensuring that users can easily structure their content and create professional technical reports using Quarto with a clear and organized structure that meets the expectations of stakeholders or publication standards. The report.qmd file should be designed to be easily maintainable and should follow best practices for Quarto document structure, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future, while also providing a clear and efficient way for users to create their reports using Quarto, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also include any necessary metadata or front matter to ensure that it is properly recognized and rendered by Quarto when the report is built, while also providing clear instructions on how to structure the content and include the various sections of the report effectively, ensuring that users can easily create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications. The report.qmd file should be an integral part of the project, serving as the main entry point for building and rendering the PDF report using Quarto, while also providing a clear and efficient way for users to structure their content and include the various sections of their reports effectively, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The report.qmd file should also be regularly reviewed and updated as needed to ensure that it remains relevant and effective in guiding users towards creating high-quality reports using Quarto, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the structure or requirements of the report.qmd file over time, ensuring that users can continue to create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications, while also providing a seamless experience when building and rendering their reports using Quarto. The report.qmd file should also include any necessary instructions or guidance on how to structure the content effectively, ensuring that users can easily create reports that are well-organized and adhere to the specified formatting and style guidelines outlined in the project requirements, while also providing clear instructions on how to include the various sections of the report using the include directive, ensuring that users can easily structure their content and create professional technical reports using Quarto with a clear and organized structure that meets the expectations of stakeholders or publication standards. The report.qmd file should be designed to be easily maintainable and should follow best practices for Quarto document structure, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future, while also providing a clear and efficient way for users to create their reports using Quarto, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also include any necessary metadata or front matter to ensure that it is properly recognized and rendered by Quarto when the report is built, while also providing clear instructions on how to structure the content and include the various sections of the report effectively, ensuring that users can easily create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications. The report.qmd file should be an integral part of the project, serving as the main entry point for building and rendering the PDF report using Quarto, while also providing a clear and efficient way for users to structure their content and include the various sections of their reports effectively, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The report.qmd file should also be regularly reviewed and updated as needed to ensure that it remains relevant and effective in guiding users towards creating high-quality reports using Quarto, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the structure or requirements of the report.qmd file over time, ensuring that users can continue to create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications, while also providing a seamless experience when building and rendering their reports using Quarto. The report.qmd file should also include any necessary instructions or guidance on how to structure the content effectively, ensuring that users can easily create reports that are well-organized and adhere to the specified formatting and style guidelines outlined in the project requirements, while also providing clear instructions on how to include the various sections of the report using the include directive, ensuring that users can easily structure their content and create professional technical reports using Quarto with a clear and organized structure that meets the expectations of stakeholders or publication standards. The report.qmd file should be designed to be easily maintainable and should follow best practices for Quarto document structure, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future, while also providing a clear and efficient way for users to create their reports using Quarto, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also include any necessary metadata or front matter to ensure that it is properly recognized and rendered by Quarto when the report is built, while also providing clear instructions on how to structure the content and include the various sections of the report effectively, ensuring that users can easily create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications. The report.qmd file should be an integral part of the project, serving as the main entry point for building and rendering the PDF report using Quarto, while also providing a clear and efficient way for users to structure their content and include the various sections of their reports effectively, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The report.qmd file should also be regularly reviewed and updated as needed to ensure that it remains relevant and effective in guiding users towards creating high-quality reports using Quarto, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the structure or requirements of the report.qmd file over time, ensuring that users can continue to create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications, while also providing a seamless experience when building and rendering their reports using Quarto. The report.qmd file should also include any necessary instructions or guidance on how to structure the content effectively, ensuring that users can easily create reports that are well-organized and adhere to the specified formatting and style guidelines outlined in the project requirements, while also providing clear instructions on how to include the various sections of the report using the include directive, ensuring that users can easily structure their content and create professional technical reports using Quarto with a clear and organized structure that meets the expectations of stakeholders or publication standards. The report.qmd file should be designed to be easily maintainable and should follow best practices for Quarto document structure, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future, while also providing a clear and efficient way for users to create their reports using Quarto, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output.

- The report should be customized to include the cover page at the top, followed by a table of contents, and then the various sections of the report as outlined in the project requirements, using the include directive to pull in the content from the respective .qmd files for each section, ensuring that the structure of the report is organized and follows the specified hierarchy, while also adhering to the overall formatting and style guidelines outlined in the project requirements to ensure that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The report.qmd file should also include any necessary metadata or front matter to ensure that it is properly recognized and rendered by Quarto when the report is built, while also providing clear instructions on how to structure the content and include the various sections of the report effectively, ensuring that users can easily create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications. The report.qmd file should be designed to be easily maintainable and should follow best practices for Quarto document structure, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future, while also providing a clear and efficient way for users to create their reports using Quarto, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also include any necessary metadata or front matter to ensure that it is properly recognized and rendered by Quarto when the report is built, while also providing clear instructions on how to structure the content and include the various sections of the report effectively, ensuring that users can easily create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications. The report.qmd file should be an integral part of the project, serving as the main entry point for building and rendering the PDF report using Quarto, while also providing a clear and efficient way for users to structure their content and include the various sections of their reports effectively, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The report.qmd file should also be regularly reviewed and updated as needed to ensure that it remains relevant and effective in guiding users towards creating high-quality reports using Quarto, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the structure or requirements of the report.qmd file over time, ensuring that users can continue to create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications, while also providing a seamless experience when building and rendering their reports using Quarto. The report.qmd file should also include any necessary instructions or guidance on how to structure the content effectively, ensuring that users can easily create reports that are well-organized and adhere to the specified formatting and style guidelines outlined in the project requirements, while also providing clear instructions on how to include the various sections of the report using the include directive, ensuring that users can easily structure their content and create professional technical reports using Quarto with a clear and organized structure that meets the expectations of stakeholders or publication standards. The report.qmd file should be designed to be easily maintainable and should follow best practices for Quarto document structure, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future, while also providing a clear and efficient way for users to create their reports using Quarto, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also include any necessary metadata or front matter to ensure that it is properly recognized and rendered by Quarto when the report is built, while also providing clear instructions on how to structure the content and include the various sections of the report effectively, ensuring that users can easily create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications. The report.qmd file should be an integral part of the project, serving as the main entry point for building and rendering the PDF report using Quarto, while also providing a clear and efficient way for users to structure their content and include the various sections of their reports effectively, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The report.qmd file should also be regularly reviewed and updated as needed to ensure that it remains relevant and effective in guiding users towards creating high-quality reports using Quarto, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the structure or requirements of the report.qmd file over time, ensuring that users can continue to create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications, while also providing a seamless experience when building and rendering their reports using Quarto. The report.qmd file should also include any necessary instructions or guidance on how to structure the content effectively, ensuring that users can easily create reports that are well-organized and adhere to the specified formatting and style guidelines outlined in the project requirements, while also providing clear instructions on how to include the various sections of the report using the include directive, ensuring that users can easily structure their content and create professional technical reports using Quarto with a clear and organized structure that meets the expectations of stakeholders or publication standards. The report.qmd file should be designed to be easily maintainable and should follow best practices for Quarto document structure, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future, while also providing a clear and efficient way for users to create their reports using Quarto, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also include any necessary metadata or front matter to ensure that it is properly recognized and rendered by Quarto when the report is built, while also providing clear instructions on how to structure the content and include the various sections of the report effectively, ensuring that users can easily create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications. The report.qmd file should be an integral part of the project, serving as the main entry point for building and rendering the PDF report using Quarto, while also providing a clear and efficient way for users to structure their content and include the various sections of their reports effectively, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The report.qmd file should also be regularly reviewed and updated as needed to ensure that it remains relevant and effective in guiding users towards creating high-quality reports using Quarto, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the structure or requirements of the report.qmd file over time, ensuring that users can continue to create professional technical reports using Quarto with a clear and organized structure that adheres to the specified requirements and guidelines outlined in the project specifications, while also providing a seamless experience when building and rendering their reports using Quarto. The report.qmd file should also include any necessary instructions or guidance on how to structure the content effectively, ensuring that users can easily create reports that are well-organized and adhere to the specified formatting and style guidelines outlined in the project requirements, while also providing clear instructions on how to include the various sections of the report using the include directive, ensuring that users can easily structure their content and create professional technical reports using Quarto with a clear and organized structure that meets the expectations of stakeholders or publication standards. The report.qmd file should be designed to be easily maintainable and should follow best practices for Quarto document structure, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future, while also providing a clear and efficient way for users to create their reports using Quarto, ultimately contributing to the overall professionalism and quality of the generated PDF output. The report.qmd file should also be tested to ensure that it works correctly with the Quarto configuration and that it produces a valid PDF output when rendered, providing a seamless experience for users when building and rendering their reports using Quarto, while also ensuring that the file is designed to be easily maintainable and adheres to the overall formatting and style guidelines outlined in the project requirements, ultimately contributing to the overall professionalism and quality of the generated PDF output.
- Example report.qmd structure with include directives for each section (ensure the paths are correct from the project structure and that the included .qmd files exist and are properly formatted to be rendered as part of the overall report.  This is just a minimal example and should be expanded to include all sections as outlined in the project requirements, ensuring that the structure of the report is organized and follows the specified hierarchy, while also adhering to the overall formatting and style guidelines outlined in the project requirements to ensure that the final output is professional, polished, and meets the expectations of stakeholders or publication standards):
```markdown
{{< include content/00_0_cover.qmd >}}

```{=latex}
\newpage
\tableofcontents
\newpage
```
```markdown

{{< include content/00_1_structure_overview.qmd >}}

{{< include content/section_01/01_0_executive_summary.qmd >}}

{{< include content/section_01/01_1_purpose_of_study.qmd >}}

{{< include content/section_01/01_2_key_findings.qmd >}}

{{< include content/section_01/01_3_recommendations.qmd >}}

{{< include content/section_02/02_0_introduction.qmd >}}

{{< include content/section_02/02_1_background.qmd >}}

{{< include content/section_02/02_2_churn_definition.qmd >}}

{{< include content/section_02/02_3_objectives.qmd >}}

{{< include content/section_02/02_4_scope.qmd >}}

{{< include content/section_02/02_5_report_structure.qmd >}}

{{< include content/section_03/03_0_literature_review.qmd >}}

{{< include content/section_03/03_1_churn_industry.qmd >}}

{{< include content/section_03/03_2_key_drivers.qmd >}}

{{< include content/section_03/03_3_ml_approaches.qmd >}}

{{< include content/section_03/03_4_gaps_justifications.qmd >}}

{{< include content/section_04/04_0_data_description.qmd >}}

{{< include content/section_04/04_1_dataset_overview.qmd >}}

{{< include content/section_04/04_2_feature_description_table.qmd >}}

{{< include content/section_04/04_3_data_quality.qmd >}}

{{< include content/section_04/04_4_data_processing_steps.qmd >}}

{{< include content/section_05/05_0_eda.qmd >}}

{{< include content/section_05/05_1_univariate_analysis.qmd >}}

{{< include content/section_05/05_2_bivariate_analysis.qmd >}}

{{< include content/section_05/05_3_correlation_analysis.qmd >}}

{{< include content/section_05/05_4_eda_summary.qmd >}}

{{< include content/section_06/06_0_methodology_model.qmd >}}

{{< include content/section_06/06_1_approach_methodology.qmd >}}

{{< include content/section_06/06_2_algorithms_selected.qmd >}}

{{< include content/section_06/06_3_evaluate_metrics.qmd >}}

{{< include content/section_06/06_4_hyperparameter_tuning.qmd >}}

{{< include content/section_06/06_5_cross_validation.qmd >}}

{{< include content/section_06/06_6_tools_libraries.qmd >}}

{{< include content/section_07/07_0_results_evaluation.qmd >}}

{{< include content/section_07/07_1_model_performance_compare.qmd >}}

{{< include content/section_07/07_2_confusion_matrix.qmd >}}

{{< include content/section_07/07_3_roc_curves.qmd >}}

{{< include content/section_07/07_4_feature_importance.qmd >}}

{{< include content/section_08/08_0_discussion.qmd >}}

{{< include content/section_08/08_1_interpret_results.qmd >}}

{{< include content/section_08/08_2_connect_literature.qmd >}}

{{< include content/section_08/08_3_limits_study.qmd >}}

{{< include content/section_09/09_0_conclusions_recommendations.qmd >}}

{{< include content/section_09/09_1_conclusions.qmd >}}

{{< include content/section_09/09_2_business_recommendations.qmd >}}

{{< include content/section_09/09_3_future_work.qmd >}}

{{< include content/section_10/10_0_references.qmd >}}

{{< include content/section_11/appendices.qmd >}}
```


## 5. Preloaded QMD Templates (🔥 most important section)
The project should include preloaded .qmd templates for each section of the report, following the structure outlined in the project requirements. Each .qmd file should include a basic template with placeholder content that can be easily modified and expanded upon by the user. The templates should be designed to provide a clear starting point for each section of the report, with appropriate headings, subheadings, and formatting to ensure consistency throughout the document. The templates should also include any necessary metadata or front matter to ensure that they are properly recognized and rendered by Quarto when the report is built. The preloaded templates should be included in the project scaffolding process, ensuring that they are generated correctly and placed in the appropriate locations within the content folder structure. The templates should be designed to be easily customizable, allowing users to modify the content and structure as needed while maintaining the overall formatting and style of the report. The templates should also be tested to ensure that they work correctly and produce the desired output when rendered as part of the overall report. The inclusion of preloaded .qmd templates is a crucial aspect of this project, as it provides users with a solid foundation for creating professional technical reports with Quarto, while also saving time and effort in setting up the initial structure and formatting of the document. Each template should be designed to be flexible and adaptable to different types of content, allowing users to easily create reports on a wide range of topics while maintaining a consistent and professional appearance throughout the document. The templates should also be designed to be easily extendable, allowing users to add additional sections or modify the existing structure as needed without requiring a complete overhaul of the project. The preloaded .qmd templates should be well-documented with comments explaining the purpose of each section and providing guidance on how to modify the content, making it easier for users to understand and utilize the templates effectively in their own projects.

See `docs/02_instructions/templates/*` for example preloaded .qmd templates for each section of the report, including the background, definitions, objectives, scope, report structure, literature review, industry analysis, key drivers, machine learning approaches, gaps and justification, data description, dataset overview, feature description, data quality, data processing steps, exploratory data analysis, univariate analysis, bivariate analysis, multivariate analysis, correlation analysis, EDA summary, methodology and model development, approach and methodology, algorithms selection, evaluation metrics, hyperparameter tuning, cross-validation, tools and libraries used in the methodology section, results and evaluation, model performance comparison, confusion matrix analysis, visualizations of results, feature importance analysis, results summary, discussion of findings and implications, interpretation of results in the context of the research questions and objectives outlined in the report. Each template includes instructions on what content to include in each section and how to structure it effectively for a professional technical report.

## 6. Style and Formatting Guidelines
The generated report should adhere to professional style and formatting guidelines, including:
- Consistent use of fonts, headings, and spacing
- Proper citation and referencing using the provided references.bib file
- Clear and concise language, avoiding jargon and unnecessary complexity
- Use of visual elements (e.g., tables, figures) to enhance readability and comprehension
- Proper use of sections and subsections to organize content logically
- Avoidance of unsupported markdown features that could cause issues in PDF rendering
- Inclusion of a title page, table of contents, and any necessary front matter
- Proper formatting of code blocks and inline code where applicable
- Use of LaTeX blocks for complex formatting needs, ensuring compatibility with PDF output
- Consistent formatting of headings and subheadings to maintain a clear hierarchy throughout the document
- Proper handling of references and citations to ensure they are correctly formatted and linked in the final PDF
- Adherence to any specific formatting requirements outlined in the project specifications or guidelines provided by the user
- Testing the final output to ensure that all formatting is correct and that the PDF renders as expected, with no broken references or formatting issues. The style and formatting guidelines should be designed to ensure that the final report is professional, polished, and suitable for presentation to stakeholders or publication, while also being easy to read and understand for a wide audience. The guidelines should be clearly documented and included in the project scaffolding process, ensuring that users have a clear reference for how to format their content and maintain consistency throughout the report. The guidelines should also be flexible enough to allow for customization and adaptation to different types of content and presentation styles, while still adhering to the core principles of professionalism and readability. The style and formatting guidelines should be an integral part of the project, ensuring that the final output meets the highest standards of quality and professionalism, while also being accessible and engaging for readers. The guidelines should be designed to be easily followed and implemented by users of all levels of experience, providing clear instructions and examples to help them create a polished and professional technical report using Quarto. The guidelines should also be regularly reviewed and updated as needed to ensure that they remain relevant and effective in guiding users towards creating high-quality reports that meet the evolving standards of technical documentation and presentation.

## 7. Build & Render Requirements
The project should be designed to support a smooth build and render process, with the following requirements:
- The project should be compatible with the latest version of Quarto and any dependencies required for building the PDF output, ensuring that it remains functional as software updates are released.
- The project should be designed to be easily built and rendered using the command `quarto render report.qmd`, with clear instructions provided in the documentation on how to execute this command and any necessary prerequisites or setup steps.
- The project should be tested to ensure that it builds and renders successfully without any errors, broken references, or missing resource paths, providing a seamless experience for users when generating the final PDF output.
- The project should include clear error handling and troubleshooting guidance in the documentation to assist users in resolving any issues that may arise during the build and render process, ensuring that they can successfully generate their reports even if they encounter challenges along the way.
- The project should be designed to be efficient and optimized for performance during the build and render process, minimizing any unnecessary operations or delays that could impact the user experience when generating the final PDF output. This may include optimizing the structure of the .qmd files, minimizing the use of complex formatting that could slow down rendering, and ensuring that all resources are properly linked and accessible during the build process. The project should also be designed to be compatible with common build and render environments, ensuring that it can be successfully built and rendered across a wide range of systems and configurations without requiring extensive modifications or troubleshooting. The build and render requirements should be clearly documented and included in the project scaffolding process, ensuring that users have a clear understanding of how to build and render their reports successfully, while also providing guidance on how to troubleshoot any issues that may arise during the process. The requirements should be designed to ensure that users can easily generate high-quality PDF reports using Quarto, with a smooth and efficient build and render process that minimizes any potential challenges or obstacles along the way. The project should be designed to be robust and reliable during the build and render process, ensuring that users can consistently generate their reports without encountering errors or issues, while also providing a professional and polished final output that meets the highest standards of quality and presentation. The build and render requirements should be an integral part of the project, ensuring that users have a clear path to successfully generating their reports and that the project is designed to support a seamless and efficient build and render process that enhances the overall user experience when working with Quarto to create professional technical reports. The requirements should also be regularly reviewed and updated as needed to ensure that they remain relevant and effective in guiding users towards successfully building and rendering their reports, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the build and render process over time. The project should be designed to be flexible and adaptable to different build and render environments, ensuring that it can be successfully built and rendered across a wide range of systems and configurations without requiring extensive modifications or troubleshooting, while still maintaining the core structure and requirements outlined in the project specifications. The build and render requirements should be designed to ensure that users can easily generate high-quality PDF reports using Quarto, with a smooth and efficient build and render process that minimizes any potential challenges or obstacles along the way, while also providing a professional and polished final output that meets the highest standards of quality and presentation. The project should be tested to ensure that it builds and renders successfully across different environments and configurations, providing a consistent and reliable experience for users when generating their reports, while also ensuring that the final output is of the highest quality and meets the expectations of stakeholders or publication standards. The build and render requirements should be clearly documented and included in the project scaffolding process, ensuring that users have a clear understanding of how to build and render their reports successfully, while also providing guidance on how to troubleshoot any issues that may arise during the process, ensuring that they can successfully generate their reports even if they encounter challenges along the way. The project should be designed to be robust and reliable during the build and render process, ensuring that users can consistently generate their reports without encountering errors or issues, while also providing a professional and polished final output that meets the highest standards of quality and presentation. The build and render requirements should be an integral part of the project, ensuring that users have a clear path to successfully generating their reports and that the project is designed to support a seamless and efficient build and render process that enhances the overall user experience when working with Quarto to create professional technical reports. The requirements should also be regularly reviewed and updated as needed to ensure that they remain relevant and effective in guiding users towards successfully building and rendering their reports, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the build and render process over time. The project should be designed to be flexible and adaptable to different build and render environments, ensuring that it can be successfully built and rendered across a wide range of systems and configurations without requiring extensive modifications or troubleshooting, while still maintaining the core structure and requirements outlined in the project specifications. The build and render requirements should be designed to ensure that users can easily generate high-quality PDF reports using Quarto, with a smooth and efficient build and render process that minimizes any potential challenges or obstacles along the way, while also providing a professional and polished final output that meets the highest standards of quality and presentation. The project should be tested to ensure that it builds and renders successfully across different environments and configurations, providing a consistent and reliable experience for users when generating their reports, while also ensuring that the final output is of the highest quality and meets the expectations of stakeholders or publication standards. The build and render requirements should be clearly documented and included in the project scaffolding process, ensuring that users have a clear understanding of how to build and render their reports successfully, while also providing guidance on how to troubleshoot any issues that may arise during the process, ensuring that they can successfully generate their reports even if they encounter challenges along the way. The project should be designed to be robust and reliable during the build and render process, ensuring that users can consistently generate their reports without encountering errors or issues,while also providing a professional and polished final output that meets the highest standards of quality and presentation. The build and render requirements should be an integral part of the project, ensuring that users have a clear path to successfully generating their reports and that the project is designed to support a seamless and efficient build and render process that enhances the overall user experience when working with Quarto to create professional technical reports. The requirements should also be regularly reviewed and updated as needed to ensure that they remain relevant and effective in guiding users towards successfully building and rendering their reports, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the build and render process over time. The project should be designed to be flexible and adaptable to different build and render environments, ensuring that it can be successfully built and rendered across a wide range of systems and configurations without requiring extensive modifications or troubleshooting, while still maintaining the core structure and requirements outlined in the project specifications. The build and render requirements should be designed to ensure that users can easily generate high-quality PDF reports using Quarto, with a smooth and efficient build and render process that minimizes any potential challenges or obstacles along the way, while also providing a professional and polished final output that meets the highest standards of quality and presentation. The project should be tested to ensure that it builds and renders successfully across different environments and configurations, providing a consistent and reliable experience for users when generating their reports, while also ensuring that the final output is of the highest quality and meets the expectations of stakeholders or publication standards. The build and render requirements should be clearly documented and included in the project scaffolding process, ensuring that users have a clear understanding of how to build and render their reports successfully, while also providing guidance on how to troubleshoot any issues that may arise during the process, ensuring that they can successfully generate their reports even if they encounter challenges along the way. The project should be designed to be robust and reliable during the build and render process, ensuring that users can consistently generate their reports without encountering errors or issues, while also providing a professional and polished final output that meets the highest standards of quality and presentation. The build and render requirements should be an integral part of the project, ensuring that users have a clear path to successfully generating their reports and that the project is designed to support a seamless and efficient build and render process that enhances the overall user experience when working with Quarto to create professional technical reports. The requirements should also be regularly reviewed and updated as needed to ensure that they remain relevant and effective in guiding users towards successfully building and rendering their reports, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the build and render process over time.

## 8. Constraints & Rules
To ensure that the project remains focused and adheres to the specified requirements, the following constraints and rules should be established:
- The project should not introduce any additional folders or files beyond what is specified in the project structure requirements, ensuring that the organization and structure of the project remains consistent and clear.
- The project should not modify the existing structure or organization of the specified folders and files, ensuring that the core structure and requirements outlined in the project specifications are maintained throughout the development process.
- The project should not use any unsupported markdown features that could cause issues in PDF rendering, ensuring that the final output is compatible with the intended format and does not encounter any rendering issues or errors during the build process.
- The project should be designed to be compatible with PDF rendering, ensuring that all content, formatting, and resources are properly handled and rendered in the final PDF output without any issues or errors, while also adhering to the style and formatting guidelines outlined in the project requirements. The constraints and rules should be clearly documented and included in the project scaffolding process, ensuring that users have a clear understanding of the limitations and guidelines they need to follow when working with the project, while also providing guidance on how to navigate and utilize the project effectively within these constraints. The constraints and rules should be designed to ensure that the project remains focused and adheres to the specified requirements, while also providing a clear framework for users to work within when creating their reports using Quarto, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards. The constraints and rules should also be regularly reviewed and updated as needed to ensure that they remain relevant and effective in guiding users towards successfully creating high-quality reports using Quarto, while also adapting to any changes or updates in the Quarto ecosystem or related technologies that may impact the project requirements or constraints over time. The project should be designed to be flexible and adaptable within the established constraints and rules, allowing users to create a wide range of reports on different topics while still adhering to the core structure and requirements outlined in the project specifications, ensuring that the project remains versatile and useful for a variety of applications while still maintaining a consistent and professional appearance throughout the final output. The constraints and rules should be an integral part of the project, ensuring that users have a clear understanding of the limitations and guidelines they need to follow when working with the project, while also providing a clear framework for users to work within when creating their reports using Quarto, ensuring that the final output is professional, polished, and meets the expectations of stakeholders or publication standards.

## 9. Expected Output
The expected output of this project is a fully functional bash script that, when executed, will generate the complete project structure for a Quarto technical report, including all necessary folders, files, and preloaded .qmd templates for each section of the report, as well as a properly configured _quarto.yml file and a references.bib file. The generated project should be ready to build and render a professional PDF report using Quarto, adhering to the specified style and formatting guidelines, and meeting all the build and render requirements outlined in the project specifications. The bash script should be designed to be easily executed on a Linux or WSL environment, with clear instructions provided in the documentation on how to run the script and any necessary prerequisites or setup steps. The generated project should be organized and structured according to the specified project structure requirements, ensuring that users have a clear and consistent framework to work within when creating their reports using Quarto. The expected output should be tested to ensure that it meets all the specified requirements and produces a valid Quarto PDF build without any errors, broken references, or missing resource paths, providing a seamless experience for users when generating their reports. The expected output should also be designed to be easily customizable and extendable, allowing users to modify the generated project structure, templates, and configuration as needed to suit their specific needs and preferences while still adhering to the core requirements and guidelines outlined in the project specifications. The expected output should be of high quality, with clean and readable code in the bash script, and well-organized and formatted content in the generated .qmd files, ensuring that users can easily understand and work with the generated project to create professional technical reports using Quarto. The expected output should be designed to provide a solid foundation for users to build upon when creating their reports, while also ensuring that the generated project is robust, reliable, and compatible with the latest versions of Quarto and any dependencies required for building the PDF output, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future. The expected output should be an integral part of the project, providing users with a clear and efficient way to generate the necessary project structure and templates for creating professional technical reports using Quarto, while also ensuring that the generated project meets all the specified requirements and provides a seamless experience for users when building and rendering their reports, ultimately resulting in a high-quality PDF output that meets the expectations of stakeholders or publication standards. The expected output should also be designed to be easily maintainable and should follow best practices for bash scripting and project organization, ensuring that users can easily understand and modify the generated script and project structure as needed to suit their specific needs and preferences while still adhering to the core requirements and guidelines outlined in the project specifications. The expected output should be tested to ensure that it works as intended and does not produce any unintended side effects when run multiple times or in different environments, providing a reliable and consistent experience for users when generating their projects using the provided bash script, while also ensuring that the generated project structure and templates are of high quality and meet the specified requirements for creating professional technical reports using Quarto. The expected output should be designed to be secure, avoiding any potential vulnerabilities or risks associated with file creation and execution, while also ensuring that the generated project structure and templates are of high quality and meet the specified requirements for creating professional technical reports using Quarto. The expected output should be an integral part of the project, providing users with a clear and efficient way to generate the necessary project structure and templates for creating professional technical reports using Quarto, while also ensuring that the generated project meets all the specified requirements and provides a seamless experience for users when building and rendering their reports, ultimately resulting in a high-quality PDF output that meets the expectations of stakeholders or publication standards. The expected output should also be designed to be easily maintainable and should follow best practices for bash scripting and project organization, ensuring that users can easily understand and modify the generated script and project structure as needed to suit their specific needs and preferences while still adhering to the core requirements and guidelines outlined in the project specifications. The expected output should be tested to ensure that it works as intended and does not produce any unintended side effects when run multiple times or in different environments, providing a reliable and consistent experience for users when generating their projects using the provided bash script, while also ensuring that the generated project structure and templates are of high quality and meet the specified requirements for creating professional technical reports using Quarto. The expected output should be designed to be secure, avoiding any potential vulnerabilities or risks associated with file creation and execution, while also ensuring that the generated project structure and templates are of high quality and meet the specified requirements for creating professional technical reports using Quarto.








