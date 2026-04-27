# ECON 3916 Final Project
## Predicting Diabetes Risk from Health and Lifestyle Indicators

## Project Overview

This project builds a machine learning model to predict whether an individual is at higher risk of diabetes using health, demographic, and behavioral indicators from the CDC Diabetes Health Indicators dataset.

This project is framed as a prediction problem, not a causal inference problem. The goal is to support early risk screening, not diagnose diabetes or prove that any individual feature causes diabetes.

## Prediction Question

Can health, demographic, and behavioral indicators predict whether an individual has diabetes?

## Stakeholder

The main stakeholder is a public health screening program, clinic, or preventive care organization that wants to identify individuals who may benefit from additional diabetes screening, preventive education, or clinical follow-up.

## Decision This Enables

This model can help stakeholders identify individuals who may be at higher risk of diabetes and prioritize follow-up screening, preventive education, and early intervention efforts.

## Dataset

This project uses the CDC Diabetes Health Indicators dataset derived from the 2015 Behavioral Risk Factor Surveillance System.

- Source: CDC Behavioral Risk Factor Surveillance System / Diabetes Health Indicators dataset
- Target variable: Diabetes_binary
- Observations: 253,680
- Predictor variables: 21
- Access date: April 2026

## Prediction vs. Causation

This project is focused on prediction, not causation. The model estimates whether a person is likely to be classified as diabetic based on observed health and lifestyle indicators. It does not prove that any individual feature causes diabetes.

Feature importance should be interpreted as predictive importance, not causal effect.

## Models Compared

Two models were compared:

1. Logistic Regression
2. Random Forest Classifier

The final model selected was balanced Logistic Regression.

Balanced Logistic Regression was selected because it performed well, was easier to interpret, was easier to deploy, and better fit the goal of a screening-support tool. In this setting, recall for the diabetes class is especially important because the goal is to identify more potentially high-risk individuals for follow-up.

## Repository Contents

This repository includes:

- 3916_final_project.ipynb — final notebook with EDA, modeling, and evaluation
- app (1).py — Streamlit dashboard application
- model.pkl — saved trained model used by the app
- requirements.txt — Python dependencies
- final_report.pdf — final project report
- ai_methodology_appendix.pdf — AI methodology appendix
- README.md — project overview and reproducibility instructions

## Streamlit Dashboard

Deployed app:

https://econ-3916-ml-prediction-project-final-project2-khuflsobpop4w9u.streamlit.app/

The dashboard allows users to adjust health, demographic, and behavioral inputs and view the model’s predicted diabetes risk. The output should be interpreted as a screening-support prediction, not a diagnosis.

## Reproducibility Instructions

Follow the steps below to reproduce the project locally.

## 1. Clone the Repository

    git clone https://github.com/rpark3/ECON-3916-ML-Prediction-Project-Final-Project2.git
    cd ECON-3916-ML-Prediction-Project-Final-Project2

## 2. Create a Virtual Environment

    python -m venv venv

## 3. Activate the Virtual Environment

On Mac/Linux:

    source venv/bin/activate

On Windows:

    venv\Scripts\activate

## 4. Install Dependencies

    pip install -r requirements.txt

## 5. Run the Jupyter Notebook

    jupyter notebook 3916_final_project.ipynb

Run the notebook from top to bottom to reproduce the exploratory data analysis, model training, model comparison, evaluation metrics, and saved model artifact.

## 6. Launch the Streamlit App Locally

Because the app file name contains spaces and parentheses, use quotation marks:

    streamlit run "app (1).py"

The Streamlit app allows users to adjust health and lifestyle inputs and view the model’s predicted diabetes risk.

## Results Summary

The Logistic Regression and Random Forest models both showed useful predictive performance. Random Forest performed slightly better by ROC-AUC, but the difference was small. Balanced Logistic Regression was selected as the final model because it performed well, was more interpretable, and was better suited for a screening-support setting.

Because this is a public health screening context, recall for the diabetes class was especially important. A model that identifies more potentially high-risk individuals is more useful for early outreach than a model that only maximizes overall accuracy.

## Recommendation

The model can be used as a screening-support tool to help identify individuals who may benefit from additional diabetes screening, preventive education, or follow-up care.

It should not replace clinical judgment. The most appropriate use case is early risk flagging in a public health or preventive care setting.

## Important Limitations

This model is intended for screening support only. It should not be used as a diagnostic tool.

Important limitations include:

- The model identifies predictive patterns, not causal effects
- Predictions depend on the quality and representativeness of the BRFSS 2015 data
- The model may not generalize perfectly to all populations, healthcare settings, or future years
- A high-risk prediction should be interpreted as a signal for possible follow-up, not as a medical diagnosis

## AI Methodology

AI tools were used as a co-pilot during the project and documented using the P.R.I.M.E. framework:

- Prep: Defined the task and project goals before prompting
- Request: Wrote specific prompts for help with coding, interpretation, debugging, or writing
- Iterate: Refined AI output when it was incomplete, unclear, or incorrect
- Mechanism Check: Verified that code worked and that outputs made sense
- Evaluate: Applied human judgment to decide what to keep, revise, or reject

The full documentation is included in the AI methodology appendix.

## Files Required to Reproduce

To reproduce the project, the following files should be present in the repository:

- 3916_final_project.ipynb
- app (1).py
- model.pkl
- requirements.txt
- final_report.pdf
- ai_methodology_appendix.pdf

## Notes for Users

This dashboard is designed for educational and analytical purposes. It should not be used to diagnose diabetes or make medical decisions. A high-risk prediction should be interpreted as a signal that further screening or clinical follow-up may be useful.
