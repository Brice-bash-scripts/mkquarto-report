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
│   │   ├── 04_2_feature_engineering.qmd
│   │   ├── 04_3_data_quality.qmd
│   │   └── 04_4_data_processing_steps.qmd
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
│   │   ├── 08_4_implications.qmd
│   │   └── 08_5_discussion_summary.qmd
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
- Directory Creation: The script should create all necessary directories if they do not already exist.
- File Generation: The script should generate all required files, including the main report.qmd, _quarto.yml, and references.bib, as well as the structured content files within the content folder.
- The script should not introduce any additional folders or files beyond what is specified in the project structure.
- The script should ensure compatibility with PDF rendering, avoiding any unsupported markdown features that could cause build failures.
- The script should include error handling to manage potential issues during execution, such as missing dependencies or permission errors.
- The script should provide clear output messages to indicate the progress of the project scaffolding process and any issues encountered.
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

## 4. Quarto Configuration (_quarto.yml)
The _quarto.yml file should be configured to support PDF output and include any necessary settings for the project. This may include specifying the output format, setting up references, and defining any custom styles or templates that should be used in the report. The configuration should be designed to ensure that the generated PDF is professional and adheres to the formatting standards outlined in the project requirements. The configuration should also be flexible enough to allow for future modifications or additions as needed, while maintaining compatibility with the overall project structure and requirements. The _quarto.yml file should be well-documented with comments explaining each setting and its purpose, making it easier for users to understand and modify as needed. The configuration should also be tested to ensure that it works correctly and produces the desired output when the report is built and rendered. The _quarto.yml file should be included in the project scaffolding process, ensuring that it is generated correctly and placed in the appropriate location within the project structure. The configuration should be designed to be easily maintainable and should follow best practices for Quarto configuration, ensuring that it remains functional and effective as the project evolves and as new features or requirements are added in the future.

- Example _quarto.yml configuration:
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

## 5. Preloaded QMD Templates (🔥 most important section)
The project should include preloaded .qmd templates for each section of the report, following the structure outlined in the project requirements. Each .qmd file should include a basic template with placeholder content that can be easily modified and expanded upon by the user. The templates should be designed to provide a clear starting point for each section of the report, with appropriate headings, subheadings, and formatting to ensure consistency throughout the document. The templates should also include any necessary metadata or front matter to ensure that they are properly recognized and rendered by Quarto when the report is built. The preloaded templates should be included in the project scaffolding process, ensuring that they are generated correctly and placed in the appropriate locations within the content folder structure. The templates should be designed to be easily customizable, allowing users to modify the content and structure as needed while maintaining the overall formatting and style of the report. The templates should also be tested to ensure that they work correctly and produce the desired output when rendered as part of the overall report. The inclusion of preloaded .qmd templates is a crucial aspect of this project, as it provides users with a solid foundation for creating professional technical reports with Quarto, while also saving time and effort in setting up the initial structure and formatting of the document. Each template should be designed to be flexible and adaptable to different types of content, allowing users to easily create reports on a wide range of topics while maintaining a consistent and professional appearance throughout the document. The templates should also be designed to be easily extendable, allowing users to add additional sections or modify the existing structure as needed without requiring a complete overhaul of the project. The preloaded .qmd templates should be well-documented with comments explaining the purpose of each section and providing guidance on how to modify the content, making it easier for users to understand and utilize the templates effectively in their own projects.

### Example preloaded .qmd template for the executive summary section (01_0_executive_summary.qmd):

- Minimum Example .qmd template for the executive summary section (01_0_executive_summary.qmd):
```markdown
# Section 1.0: Executive Summary
This section provides a concise overview of the key findings and recommendations of the report. It is intended to give readers a quick understanding of the main points without needing to read the entire document. The executive summary should be clear, concise, and free of technical jargon, making it accessible to a wide audience. It should Provide a concise standalone summary (200–300 words) that covers: the problem, dataset, methods used, key findings, and your main recommendation. No citations are needed here.
A business manager should be able to read this and understand your entire project.

<!-- 
INSTRUCTIONS:
- Summarize key findings
- 3–5 bullet points
- No technical jargon
-->

[Insert content here]

- You’re not just scaffolding files.
- You’re scaffolding thinking.
```

### Example preloaded .qmd template for the purpose of study section (01_1_purpose_of_study.qmd):
```markdown
# 1.1 Purpose of Study
This section should clearly articulate the motivation behind the study, outlining the specific problem or question that the report aims to address. It should provide context for the research, explaining why the topic is important and relevant to the intended audience. The purpose of the study should be clearly defined, with specific objectives and goals that guide the research process. This section should also highlight any gaps in existing knowledge or research that the study aims to fill, providing a rationale for why the research is necessary and valuable. The purpose of the study should be concise and focused, providing a clear direction for the rest of the report while also engaging the reader and encouraging them to continue reading to learn more about the research and its findings.

<!-- 
INSTRUCTIONS:
- Clearly state the motivation for the study
- Define the specific problem or question being addressed
- Provide context and relevance to the intended audience
- Highlight any gaps in existing knowledge that the study aims to fill
- Keep it concise and focused
-->
[Insert content here]
```
### Example preloaded .qmd template for the key findings section (01_2_key_findings.qmd):
```markdown
# 1.2 Key Findings
This section should present the main findings of the study in a clear and concise manner. It should summarize the key results and insights that were discovered during the research process, highlighting any significant trends, patterns, or relationships that were identified. The key findings should be presented in a logical and organized manner, using appropriate headings and subheadings to guide the reader through the content. This section should also include any relevant data visualizations or tables that help to illustrate the findings and make them easier to understand. The key findings should be presented in a way that is accessible to a wide audience, avoiding technical jargon and focusing on the most important insights that were uncovered during the research.

<!-- 
INSTRUCTIONS:
- Summarize the main findings of the study
- Highlight significant trends, patterns, or relationships
- Use clear and concise language
- Include relevant data visualizations or tables
- Avoid technical jargon
-->
[Insert content here]
•	[Key finding 1 — e.g., overall $study$ rate was X%]
•	[Key finding 2 — e.g., top predictor was contract type]
•	[Key finding 3 — e.g., best model achieved X% accuracy / AUC of X]
```

### Example preloaded .qmd template for the recommendations section (01_3_recommendations.qmd):
```markdown
# 1.3 Recommendations
This section should provide actionable recommendations based on the key findings of the study. The recommendations should be specific, practical, and directly tied to the insights uncovered during the research process. Each recommendation should be clearly articulated, with a rationale that explains why it is being made and how it can be implemented. The recommendations should be prioritized based on their potential impact and feasibility, with the most important and impactful recommendations presented first. This section should also include any potential challenges or considerations that may arise when implementing the recommendations, along with suggestions for how to address them. The recommendations should be presented in a way that is accessible to a wide audience, avoiding technical jargon and focusing on practical steps that can be taken to address the issues identified in the study.

<!-- 
INSTRUCTIONS:
- Provide actionable recommendations based on key findings
- Clearly articulate each recommendation with a rationale
- Prioritize recommendations based on impact and feasibility
- Include potential challenges and suggestions for implementation
- Avoid technical jargon and focus on practical steps
-->
[Insert content here]
- [Recommendation 1 — e.g., implement X to reduce $study$ rate by Y%]
- [Recommendation 2 — e.g., focus on improving contract type to reduce $study$ rate]
- [Recommendation 3 — e.g., further investigate top predictors to identify additional opportunities for improvement]
```

### Example preloaded .qmd template for the introduction section (02_0_introduction.qmd):
```markdown
# Section 2.0: Introduction
The introduction section should provide an overview of the report, setting the stage for the reader and providing context for the research that will be presented. It should introduce the topic of the report, explaining why it is important and relevant to the intended audience. The introduction should also outline the structure of the report, providing a roadmap for the reader to follow as they navigate through the content. This section should be engaging and informative, capturing the reader's attention and encouraging them to continue reading to learn more about the research and its findings. The introduction should be concise and focused, providing enough information to orient the reader without overwhelming them with details that will be covered in later sections of the report.

<!--
INSTRUCTIONS:
- Introduce the topic and its relevance
- Provide context for the research
- Outline the structure of the report
- Engage the reader and encourage them to continue reading
- Keep it concise and focused
-->
[Insert content here]
```

### Example preloaded .qmd template for the background section (02_1_background.qmd):
```markdown
# 2.1 Background & Business Context
This section should provide a comprehensive background on the topic being studied, including any relevant historical information, industry context, or previous research that has been conducted in the area. It should explain the broader business context in which the research is situated, highlighting any relevant trends, challenges, or opportunities that are driving the need for the study. The background section should also provide an overview of the specific problem or question being addressed in the report, explaining why it is important and how it fits into the larger context of the industry or field. This section should be well-researched and should include citations to relevant sources to support the information presented. The background should be written in a way that is accessible to a wide audience, avoiding technical jargon and focusing on providing a clear and comprehensive overview of the topic and its relevance to the intended audience. Suggested length: 400–600 words.
<!--
INSTRUCTIONS:
- Provide comprehensive background on the topic
- Explain the broader business context
- Highlight relevant trends, challenges, or opportunities
- Provide an overview of the specific problem or question being addressed
- Include citations to relevant sources
- Avoid technical jargon and focus on clarity
-->
[Insert content here]
```

### Example preloaded .qmd template for the background section (02_2_definitions.qmd):
```markdown
# 2.2 Definitions & Terminology
This section should provide clear definitions and explanations of any key terms, concepts, or terminology that will be used throughout the report. It should ensure that readers have a common understanding of the language and concepts being used, which is essential for effective communication and comprehension of the report's content. The definitions should be concise and straightforward, avoiding technical jargon where possible and providing examples or explanations to clarify any complex terms or concepts. This section should be organized in a way that is easy to navigate, with clear headings and subheadings to guide the reader through the content. The definitions should be relevant to the specific topic being studied and should be tailored to the intended audience, ensuring that they are accessible and understandable to a wide range of readers. This section should also include any relevant citations or references to support the definitions provided, ensuring that they are grounded in established knowledge and research in the field. Suggested length: 300–500 words.
<!--
INSTRUCTIONS:
- Provide clear definitions of key terms and concepts
- Ensure a common understanding of language and concepts
- Avoid technical jargon and provide examples where necessary
- Organize content with clear headings and subheadings
- Tailor definitions to the intended audience
- Include citations or references to support definitions
-->
[Insert content here]   
```

