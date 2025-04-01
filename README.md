# An-Empirical-Research-Study-of-ChatGPT-4o-Use-in-Engineering-Education
AI Interaction and Writing Metrics Pipeline
This repository contains the full data processing pipeline, metric computation scripts, and interface code used in a study examining AI (ChatGPT-4o) prompting behaviors and writing performance among engineering students.

Structure
The codebase is divided into logical modules that reflect the complete workflow:

1. Interface
Interface Python Code: A GUI tool used by students to interact with ChatGPT-4o. Prompts and responses are logged with timestamps, course, session, and activity type. Logs are automatically emailed to the researcher on session close.

2. Data Merging
parse_ai_logs: Parses raw .txt files to extract prompts/responses, remove near-duplicates, and compile block-formatted logs.

convert_assignments: Converts .docx student submissions to .json format with cleaned text.

convert_grades: Converts Excel grade sheet to structured JSON.

merge all data: Merges prompt logs, AI responses, assignments, and grades into a unified dataset.

3. Writing Quality Metrics
SC - compute_structural_complexity: Calculates sentence-level grammatical and syntactic complexity.

CR - compute_content_richness: Computes lexical diversity and content density.

4. AI Interaction Metrics
ARR - compute_text_similarity

ARR - compute_copy_paste_score

ARR - compute_structural_similarity

ARR - compute_prompt_response_consistency

ARR - compute_query_submission_link

ARR - compute_ai_response_reliance: Combines all five sub-scores into final ARR score.

QD - compute_lexical_structure

QD - compute_multistep_depth

QD - compute_focus_clarity

QD - compute_query_depth: Aggregates all three components into QD score.

QE - compute_query_efficiency: Computes QD-to-query ratio.

PRD - compute_prompt_refinement_depth: Measures semantic and structural prompt improvements.

RU - compute_semantic_novelty

RU - compute_conceptual_transformation

RU - compute_contribution_final

RU - compute_response_utility: Combines all into final utility score.

PS - compute_stepwise_alignment

PS - compute_conceptual_application

PS - compute_independent_expansion

PS - compute_problem_solving_score: Combines all three into final PS score.

5. Final Output
Final Dataset - final_export_to_excel: Combines all fields and metrics into a structured .xlsx file for statistical analysis.

Dependencies
Python 3.8+

pandas, openpyxl, docx, Levenshtein, spacy, nltk, scikit-learn, sentence-transformers, tqdm, smtplib

Notes
The code was designed to process over 900 AI-access sessions and 1800+ written assignments.

Metric columns are populated with zeros if students were absent or didn’t have AI access.

All logs and metrics are aligned per student ID, session number, and course type.
