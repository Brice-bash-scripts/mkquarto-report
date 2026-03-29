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
│   │   ├── 04_2_feature_description.qmd
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

### Example preloaded .qmd template for the objectives section (02_3_objectives.qmd):
```markdown
# 2.3 Objectives & Research Questions
This section should clearly outline the specific objectives and research questions that the report aims to address. The objectives should be specific, measurable, achievable, relevant, and time-bound (SMART), providing a clear framework for the research process and guiding the analysis and interpretation of the findings. The research questions should be directly tied to the objectives, providing a clear focus for the study and ensuring that the research is structured and organized in a way that allows for meaningful insights to be derived from the data. The objectives and research questions should be presented in a way that is accessible to a wide audience, avoiding technical jargon and focusing on clarity and relevance. This section should also include any relevant citations or references to support the objectives and research questions, ensuring that they are grounded in established knowledge and research in the field. Suggested length: 300–500 words.
<!--
INSTRUCTIONS:
- Clearly outline specific objectives and research questions
- Ensure objectives are SMART (Specific, Measurable, Achievable, Relevant, Time-bound)
- Tie research questions directly to objectives
- Avoid technical jargon and focus on clarity
- Include citations or references to support objectives and research questions
-->
[Insert content here]
- Objective 1: [e.g., Analyze the factors contributing to $study$ rate in the telecommunications industry]
- Objective 2: [e.g., Evaluate the performance of different machine learning models in predicting $study$]
- Objective 3: [e.g., Provide actionable recommendations to reduce $study$ rate based on key findings]
- Research Question 1: [e.g., What are the main factors contributing to $study$ rate in the telecommunications industry?]
- Research Question 2: [e.g., Which machine learning models perform best in predicting $study$?]
- Research Question 3: [e.g., What actionable recommendations can be made to reduce $study$ rate based on the key findings?]
```

### Example preloaded .qmd template for the scope section (02_4_scope.qmd):
```markdown
# 2.4 Scope & Limitations
This section should clearly define the scope of the study, outlining the specific boundaries and parameters within which the research will be conducted. It should specify the population, sample, or data that will be analyzed, as well as any specific timeframes, geographic locations, or other relevant factors that will be considered in the study. The scope should be clearly defined to ensure that the research is focused and manageable, while also providing enough flexibility to allow for meaningful insights to be derived from the data. This section should also acknowledge any limitations or constraints that may impact the research, such as data availability, methodological constraints, or potential biases. It should provide a transparent and honest assessment of the limitations of the study, while also highlighting any steps that were taken to mitigate these limitations and ensure the validity and reliability of the findings. The scope and limitations should be presented in a way that is accessible to a wide audience, avoiding technical jargon and focusing on clarity and transparency. This section should also include any relevant citations or references to support the scope and limitations outlined, ensuring that they are grounded in established knowledge and research in the field. Suggested length: 300–500 words.
<!--
INSTRUCTIONS:
- Clearly define the scope of the study, including boundaries and parameters
- Specify population, sample, data, timeframes, geographic locations, etc.
- Acknowledge limitations or constraints that may impact the research
- Provide a transparent assessment of limitations and steps taken to mitigate them
- Avoid technical jargon and focus on clarity and transparency
- Include citations or references to support the scope and limitations outlined
-->
[Insert content here]
- Scope: [e.g., The study will analyze customer data from a telecommunications company over a one-year period, focusing on factors contributing to customer churn (study) and evaluating machine learning models for prediction. The analysis will be limited to customers in the United States and will not include data from other geographic regions or industries.]
- Limitations: [e.g., The study may be limited by the availability and quality of the data, potential biases in the sample, and methodological constraints that may impact the generalizability of the findings. Additionally, the study may not account for all potential factors contributing to customer churn, and the recommendations provided may not be applicable to all contexts or industries.]
```

### Example preloaded .qmd template for the report structure section (02_5_report_structure.qmd):
```markdown
# 2.5 Report Structure & Organization
This section should provide an overview of the structure and organization of the report, outlining how the content is organized and what readers can expect to find in each section. It should provide a roadmap for the reader, guiding them through the different sections of the report and explaining how each section contributes to the overall narrative and flow of the document. The report structure should be designed to be logical and coherent, with clear headings and subheadings that help to organize the content and make it easy to navigate. This section should also highlight any key features or elements of the report, such as data visualizations, tables, or appendices, and explain how they are integrated into the overall structure of the document. The report structure should be presented in a way that is accessible to a wide audience, avoiding technical jargon and focusing on clarity and organization. This section should also include any relevant citations or references to support the structure and organization outlined, ensuring that it is grounded in established knowledge and research in the field. Suggested length: 300–500 words.
<!--
INSTRUCTIONS:
- Provide an overview of the report structure and organization
- Guide readers through the different sections of the report
- Explain how each section contributes to the overall narrative and flow
- Use clear headings and subheadings to organize content
- Highlight key features or elements of the report (e.g., data visualizations, tables, appendices)
- Avoid technical jargon and focus on clarity and organization
- Include citations or references to support the structure and organization outlined
-->
[Insert content here]
- The report is organized into several sections, each focusing on a specific aspect of the research process and findings. The sections include:
  - Executive Summary: A concise overview of the key findings and recommendations of the report.
  - Introduction: An introduction to the topic and context of the research.
  - Background & Business Context: A comprehensive background on the topic, including industry context and previous research.
  - Definitions & Terminology: Clear definitions of key terms and concepts used throughout the report.
  - Objectives & Research Questions: Specific objectives and research questions that guide the study.
  - Scope & Limitations: A clear definition of the scope of the study and acknowledgment of any limitations or constraints.
  - Report Structure & Organization: An overview of how the report is structured and organized, guiding readers through the content.
  - Literature Review: A review of relevant literature and research in the field.
  - Data Description: An overview of the data used in the study, including its source, structure, and any preprocessing steps taken.
  - Exploratory Data Analysis: An analysis of the data to uncover patterns, trends, and insights that inform the research.
  - Methodology & Model Development: A description of the methodology used in the study, including the machine learning models developed and evaluated.
  - Results & Evaluation: A presentation of the results of the study, including an evaluation of the model performance and key findings.
  - Discussion: An interpretation of the results, connecting them to the broader context and literature, and discussing any implications or limitations.
  - Conclusions & Recommendations: A summary of the conclusions drawn from the study and actionable recommendations based on the findings.
```

### Example preloaded .qmd template for the literature review section (03_0_literature_review.qmd):
```markdown
# Section 3.0: Literature Review
This section should provide a comprehensive review of the relevant literature and research in the field related to the topic being studied. It should summarize and synthesize the key findings, theories, and methodologies from previous research, highlighting how they relate to the current study and providing a foundation for the research questions and objectives outlined in the report. The literature review should be organized thematically or chronologically, depending on the nature of the research and the available literature, and should include clear headings and subheadings to guide the reader through the content. This section should also critically evaluate the existing literature, identifying any gaps, inconsistencies, or areas for further research that the current study aims to address. The literature review should be well-researched and should include citations to relevant sources to support the information presented, ensuring that it is grounded in established knowledge and research in the field. The literature review should be written in a way that is accessible to a wide audience, avoiding technical jargon and focusing on providing a clear and comprehensive overview of the relevant literature and its relevance to the current study. Use a minimum of 8 - 10 peer-reviewed sources. Suggested length: 800–1200 words.
<!--
INSTRUCTIONS:
- Provide a comprehensive review of relevant literature and research
- Summarize and synthesize key findings, theories, and methodologies from previous research
- Organize the literature review thematically or chronologically
- Critically evaluate the existing literature, identifying gaps and areas for further research
- Include citations to relevant sources to support the information presented
- Avoid technical jargon and focus on clarity and accessibility
-->
[Insert content here]
```

### Example preloaded .qmd template for the industry analysis section (03_1_industry_analysis.qmd):
```markdown
# 3.1 Industry Analysis
This section should provide an analysis of the industry related to the topic being studied, highlighting any relevant trends, challenges, or opportunities that are driving the need for the research. It should provide an overview of the industry landscape, including key players, market dynamics, and any relevant regulatory or economic factors that may impact the research and its findings. The industry analysis should be well-researched and should include citations to relevant sources to support the information presented, ensuring that it is grounded in established knowledge and research in the field. This section should be written in a way that is accessible to a wide audience, avoiding technical jargon and focusing on providing a clear and comprehensive overview of the industry context for the research. The industry analysis should also highlight any specific challenges or opportunities that are relevant to the research questions and objectives outlined in the report, providing a clear rationale for why the research is necessary and valuable in the context of the industry. Suggested length: 400–600 words.
<!--
INSTRUCTIONS:
- Provide an analysis of the industry related to the topic being studied
- Highlight relevant trends, challenges, or opportunities driving the need for research
- Provide an overview of the industry landscape, including key players and market dynamics
- Include citations to relevant sources to support the information presented
- Avoid technical jargon and focus on clarity and accessibility
- Highlight specific challenges or opportunities relevant to the research questions and objectives
-->
[Insert content here]
```

### Example preloaded .qmd template for the key drivers section (03_2_key_drivers.qmd):
```markdown
# 3.2 Key Drivers & Factors
This section should identify and analyze the key drivers and factors that are relevant to the topic being studied. It should provide a detailed examination of the various elements that contribute to the phenomenon being researched, highlighting any significant trends, patterns, or relationships that have been identified in the data or in previous research. The key drivers and factors should be presented in a way that is accessible to a wide audience, avoiding technical jargon and focusing on clarity and relevance. This section should also include any relevant data visualizations or tables that help to illustrate the key drivers and factors, making it easier for readers to understand the relationships and insights being presented. The analysis of the key drivers and factors should be grounded in established knowledge and research in the field, with citations to relevant sources to support the information presented. This section should provide a clear and comprehensive overview of the key drivers and factors that are relevant to the research questions and objectives outlined in the report, providing a foundation for the analysis and interpretation of the findings in later sections. Suggested length: 400–600 words.
<!--
INSTRUCTIONS:
- Identify and analyze key drivers and factors relevant to the topic
- Highlight significant trends, patterns, or relationships
- Avoid technical jargon and focus on clarity and relevance
- Include relevant data visualizations or tables to illustrate key drivers and factors
- Ground analysis in established knowledge and research with citations
- Provide a clear overview of key drivers and factors relevant to research questions and objectives
-->
[Insert content here]
- Driver 1: [e.g., Customer demographics, such as age and income level, have been identified as key drivers of customer churn in the telecommunications industry.]
- Driver 2: [e.g., Service quality, including factors such as network reliability and customer support, has been shown to significantly impact customer satisfaction and retention.]
- Driver 3: [e.g., Pricing and contract terms have been found to be important factors influencing customer decisions to stay with or leave a telecommunications provider.]
- Driver 4: [e.g., Competitor offerings and market dynamics can also play a role in customer churn, as customers may be attracted to better deals or services offered by competitors.]
- Driver 5: [e.g., Customer engagement and communication strategies can influence customer loyalty and retention, with proactive communication and personalized offers being effective in reducing churn.]
```

### Example preloaded .qmd template for the machine learning approach section (03_3_machine_learning_approach.qmd):
```markdown
# 3.3 Machine Learning Approaches
Review studies that have applied ML to $study$ prediction. Discuss the models used, datasets, performance metrics, and their findings. Compare approaches critically.  Suggested length: 400–600 words.
<!--
INSTRUCTIONS:
- Review studies that have applied machine learning to $study$ prediction
- Discuss the models used, datasets, performance metrics, and findings of each study
- Compare approaches critically, highlighting strengths and weaknesses
- Avoid technical jargon and focus on clarity and relevance
- Include citations to relevant sources to support the information presented
-->
[Insert content here]
- Study 1: [e.g., Smith et al. (2020) applied logistic regression to predict customer churn using a dataset of 10,000 customers, achieving an accuracy of 85%.]
- Study 2: [e.g., Johnson and Lee (2021) used a random forest model on a dataset of 50,000 customers, reporting an AUC of 0.90.]
- Study 3: [e.g., Brown et al. (2019) implemented a support vector machine (SVM) on a dataset of 20,000 customers, achieving an accuracy of 80% but with a high false positive rate.]
- Study 4: [e.g., Davis and Miller (2022) utilized a neural network on a dataset of 100,000 customers, reporting an AUC of 0.92 but with significant computational requirements.]
- Study 5: [e.g., Wilson et al. (2020) applied gradient boosting machines to predict customer churn, achieving an accuracy of 88% and identifying key predictors such as service quality and pricing.]
```

### Example preloaded .qmd template for the gaps and justification section (03_4_gaps_and_justification.qmd):
```markdown
# 3.4 Gaps in Literature & Justification for Study
Identify gaps in the existing literature that your study aims to fill. Justify why your research is necessary and how it contributes to the field. Suggested length: 300–500 words.
<!--
INSTRUCTIONS:
- Identify gaps in the existing literature that the study aims to fill
- Justify the necessity of the research and its contribution to the field
- Avoid technical jargon and focus on clarity and relevance
- Include citations to relevant sources to support the justification
-->
[Insert content here]
- Gap 1: [e.g., While several studies have applied machine learning to predict customer churn, there is a lack of research specifically focused on the telecommunications industry, which has unique characteristics and challenges that may impact churn prediction.]
- Gap 2: [e.g., Many existing studies have focused on traditional machine learning models, with limited research on the application of more advanced techniques such as deep learning or ensemble methods in the context of customer churn prediction.]
- Gap 3: [e.g., There is a need for more research that integrates both quantitative and qualitative data to provide a more comprehensive understanding of the factors driving customer churn and to develop more effective predictive models.]
- Justification: [e.g., This study aims to address these gaps by applying a range of machine learning techniques to a large dataset of telecommunications customers, with the goal of improving the accuracy of churn prediction and providing actionable insights for reducing churn in the industry. By filling these gaps, this research will contribute to the field by advancing our understanding of customer churn in the telecommunications industry and by demonstrating the potential of advanced machine learning techniques for improving predictive performance in this context.]
```

### Example preloaded .qmd template for the data description section (04_0_data_description.qmd):
```markdown
# Section 4.0: Data Description & Preprocessing
This section should provide a detailed description of the data used in the study, including its source, structure, and any preprocessing steps that were taken to prepare the data for analysis. It should explain the characteristics of the dataset, such as the number of observations, the types of variables included, and any relevant metadata that provides context for the data. The data description should also include any preprocessing steps that were taken to clean, transform, or prepare the data for analysis, such as handling missing values, encoding categorical variables, or normalizing numerical features. This section should be written in a way that is accessible to a wide audience, avoiding technical jargon and focusing on providing a clear and comprehensive overview of the data used in the study. It should also include any relevant citations or references to support the information presented, ensuring that it is grounded in established knowledge and research in the field. The data description should provide a clear and comprehensive overview of the dataset, its characteristics, and the preprocessing steps taken, providing a foundation for the analysis and interpretation of the findings in later sections. Suggested length: 400–600 words.
<!--
INSTRUCTIONS:
- Provide a detailed description of the data used in the study, including source and structure
- Explain characteristics of the dataset, such as number of observations and types of variables
- Describe any preprocessing steps taken to prepare the data for analysis
- Avoid technical jargon and focus on clarity and accessibility
- Include citations or references to support the information presented
- Provide a clear overview of the dataset and preprocessing steps to set the foundation for analysis and interpretation of findings
-->
[Insert content here]
- Data Source: [e.g., The dataset used in this study was obtained from a telecommunications company and includes customer information, service usage data, and churn status for a period of one year.]
- Data Structure: [e.g., The dataset consists of 100,000 observations and includes 20 variables, such as customer demographics (age, income level), service usage metrics (call duration, data usage), and churn status (binary variable indicating whether the customer churned or not).]
- Preprocessing Steps: [e.g., The data was cleaned by handling missing values through imputation, encoding categorical variables using one-hot encoding, and normalizing numerical features to ensure that they are on a comparable scale for analysis. Additionally, outliers were identified and handled appropriately to prevent them from skewing the analysis.]
```

### Example preloaded .qmd template for the exploratory data overview section (04_1_data_overview.qmd):
```markdown
# 4.1 Dataset Overview
This section should provide an overview of the dataset, including any relevant summary statistics, distributions, or visualizations that help to characterize the data and provide insights into its structure and characteristics. It should include descriptive statistics such as mean, median, standard deviation, and range for numerical variables, as well as frequency counts and percentages for categorical variables. The dataset overview should also include any relevant visualizations, such as histograms, box plots, or scatter plots, that help to illustrate the distribution of the data and any relationships between variables. This section should be written in a way that is accessible to a wide audience, avoiding technical jargon and focusing on providing a clear and comprehensive overview of the dataset. It should also include any relevant citations or references to support the information presented, ensuring that it is grounded in established knowledge and research in the field. The dataset overview should provide a clear and comprehensive understanding of the data being analyzed, setting the stage for the analysis and interpretation of the findings in later sections. Suggested length: 400–600 words.
<!--
INSTRUCTIONS:
- Provide an overview of the dataset, including summary statistics and visualizations
- Include descriptive statistics for numerical and categorical variables
- Use visualizations to illustrate the distribution of the data and relationships between variables
- Avoid technical jargon and focus on clarity and accessibility
- Include citations or references to support the information presented
- Provide a clear understanding of the dataset to set the stage for analysis and interpretation of findings
-->
[Insert content here]
- Summary Statistics: [e.g., The average age of customers in the dataset is 35 years, with a standard deviation of 10 years. The median income level is $50,000, with a range of $20,000 to $100,000. The churn rate in the dataset is 20%, with 20,000 customers identified as churned and 80,000 customers identified as retained.]
- Visualizations: [e.g., A histogram of customer ages shows a normal distribution, while a box plot of income levels reveals the presence of outliers. A scatter plot of call duration versus data usage indicates a positive correlation between these two variables, suggesting that customers who use more data also tend to have longer call durations.]
```

### Example preloaded .qmd template for the feature description section (04_2_feature_description.qmd):
```markdown
# 4.2 Feature Description Table & Engineering
This section should provide a detailed description of the features used in the analysis, including their definitions, types, and any relevant transformations or engineering that was performed on the features. It should include a table that lists each feature, along with its definition, data type (e.g., numerical, categorical),and any transformations or engineering that were applied to the feature (e.g., log transformation, one-hot encoding). The feature description should also include any relevant visualizations or examples that help to illustrate the characteristics of the features and how they were transformed or engineered for analysis. This section should be written in a way that is accessible to a wide audience, avoiding technical jargon and focusing on providing a clear and comprehensive overview of the features used in the analysis. It should also include any relevant citations or references to support the information presented, ensuring that it is grounded in established knowledge and research in the field. The feature description should provide a clear and comprehensive understanding of the features used in the analysis, setting the stage for the analysis and interpretation of the findings in later sections. Suggested length: 400–600 words.
<!--
INSTRUCTIONS:
- Provide a detailed description of the features used in the analysis, including definitions and types
- Include a table listing each feature, its definition, data type, and any transformations or engineering applied
- Use visualizations or examples to illustrate the characteristics of the features and transformations
- Avoid technical jargon and focus on clarity and accessibility
- Include citations or references to support the information presented
- Provide a clear understanding of the features used in the analysis to set the stage for analysis and interpretation of findings
-->
[Insert content here]
| Feature Name | Definition | Data Type | Transformations/Engineering |
|--------------|------------|-----------|-----------------------------|
| Age          | Age of the customer in years | Numerical | None |
| Income Level | Annual income of the customer | Numerical | Log transformation applied to reduce skewness |
| Call Duration | Total duration of calls made by the customer in minutes | Numerical | None |
| Data Usage | Total data usage by the customer in gigabytes | Numerical | None |
| Churn Status | Binary variable indicating whether the customer churned (1) or not (0) | Categorical | One-hot encoding applied for analysis |
| Service Quality | Customer's rating of service quality on a scale of 1 to 5 | Numerical | None |
| Contract Type | Type of contract the customer has (e.g., month-to-month, one-year, two-year) | Categorical | One-hot encoding applied for analysis |
| Customer Engagement | Measure of customer engagement based on interactions with the company (e.g., number of support tickets, frequency of communication) | Numerical | None |
```

### Example preloaded .qmd template for the data quality section (04_3_data_quality.qmd):
```markdown
# 4.3 Data Quality & Issues
This section should assess the quality of the data used in the study, identifying any issues or challenges that may impact the analysis and interpretation of the findings. It should evaluate the completeness, accuracy, and reliability of the data, identifying any missing values, outliers, or inconsistencies that may need to be addressed in the analysis. The data quality assessment should also include any relevant visualizations or tables that help to illustrate the data quality issues and their potential impact on the analysis. This section should be written in a way that is accessible to a wide audience, avoiding technical jargon and focusing on providing a clear and comprehensive overview of the data quality issues and their implications for the analysis. It should also include any relevant citations or references to support the information presented, ensuring that it is grounded in established knowledge and research in the field. The data quality assessment should provide a clear understanding of the issues and challenges associated with the data, allowing readers to interpret the findings in the context of these limitations and to understand the steps taken to address these issues in the analysis. Suggested length: 400–600 words.
<!--
INSTRUCTIONS:
- Assess the quality of the data, identifying issues that may impact analysis and interpretation
- Evaluate completeness, accuracy, and reliability of the data, identifying missing values, outliers, or inconsistencies
- Use visualizations or tables to illustrate data quality issues and their potential impact
- Avoid technical jargon and focus on clarity and accessibility
- Include citations or references to support the information presented
- Provide a clear understanding of data quality issues and their implications for analysis and interpretation of findings
-->
[Insert content here]
- Data Completeness: [e.g., The dataset contains some missing values, particularly in the income level variable, which may impact the analysis. Imputation techniques were applied to address these missing values, but it is important to acknowledge that this may introduce some bias into the analysis.]
- Data Accuracy: [e.g., There are some inconsistencies in the data, such as customers with negative call durations or data usage, which were identified as data entry errors. These inconsistencies were addressed by removing the affected observations from the analysis, but it is important to consider the potential impact of these errors on the findings.]
- Data Reliability: [e.g., The data was collected from a single telecommunications company, which may limit the generalizability of the findings to other companies or industries. Additionally, the data may be subject to biases, such as selection bias or reporting bias, which could impact the reliability of the findings.]
- Visualizations: [e.g., A histogram of the income level variable shows a significant number of missing values, while a box plot of call duration reveals the presence of outliers. A scatter plot of data usage versus call duration indicates some inconsistencies in the data, with some customers having negative values for these variables, suggesting data entry errors.]
```

### Example preloaded .qmd template for the data preprocessing section (04_4_data_preprocessing.qmd):
```markdown
# 4.4 Data Preprocessing Steps
This section should provide a detailed description of the data preprocessing steps that were taken to prepare the data for analysis. It should explain the specific techniques and methods used to clean, transform, and prepare the data, such as handling missing values, encoding categorical variables, normalizing numerical features, and addressing outliers. The data preprocessing steps should be described in a way that is accessible to a wide audience,avoiding technical jargon and focusing on providing a clear and comprehensive overview of the preprocessing techniques used. This section should also include any relevant visualizations or examples that help to illustrate the preprocessing steps and their impact on the data, making it easier for readers to understand the transformations that were applied to the data. It should also include any relevant citations or references to support the information presented, ensuring that it is grounded in established knowledge and research in the field. The data preprocessing description should provide a clear and comprehensive understanding of the techniques used to prepare the data for analysis, allowing readers to understand the steps taken to ensure the quality and suitability of the data for analysis and interpretation of the findings in later sections. Suggested length: 400–600 words.
<!--
INSTRUCTIONS:
- Provide a detailed description of the data preprocessing steps taken to prepare the data for analysis
- Explain techniques used to clean, transform, and prepare the data (e.g., handling missing values, encoding categorical variables, normalizing numerical features, addressing outliers)
- Avoid technical jargon and focus on clarity and accessibility
- Include visualizations or examples to illustrate preprocessing steps and their impact on the data
- Include citations or references to support the information presented
- Provide a clear understanding of preprocessing techniques used to prepare the data for analysis and interpretation of findings
-->
[Insert content here]
- Handling Missing Values: [e.g., Missing values in the income level variable were addressed using mean imputation, where the missing values were replaced with the mean income level of the dataset. This technique was chosen for its simplicity and effectiveness in maintaining the overall distribution of the data, although it is important to acknowledge that it may introduce some bias into the analysis.]
- Encoding Categorical Variables: [e.g., Categorical variables such as churn status and contract type were encoded using one-hot encoding, which creates binary variables for each category. This technique allows for the inclusion of categorical variables in machine learning models while avoiding issues with ordinal encoding and ensuring that the models can capture the relationships between categories effectively.]
- Normalizing Numerical Features: [e.g., Numerical features such as income level were normalized using a log transformation to reduce skewness and improve the performance of machine learning models. This transformation helps to ensure that the numerical features are on a comparable scale and can improve the accuracy of the models.]
- Addressing Outliers: [e.g., Outliers in the call duration variable were identified using box plots and were addressed by capping the values at the 95th percentile. This technique helps to reduce the influence of extreme values on the analysis while retaining the overall structure of the data.]
- Visualizations: [e.g., A histogram of the income level variable before and after imputation shows how the missing values were addressed, while a box plot of call duration before and after outlier treatment illustrates the impact of capping on the distribution of the data.]
- Train / test split: [e.g., The dataset was split into a training set (80%) and a test set (20%) to allow for the evaluation of machine learning models on unseen data. This split helps to ensure that the models are evaluated on their ability to generalize to new data, providing a more accurate assessment of their performance.]
```



