# # Student-Performance-Prediction
An end-to-end Machine Learning project that predicts a student's math exam score based on demographic and academic factors. It includes a complete ML pipeline — from data ingestion and preprocessing to model training, evaluation, and a live Flask web app for predictions.
---
📌 Problem Statement
Given information about a student (gender, ethnicity, parental education, lunch type, test preparation, reading score, and writing score), predict their math score.


🗂️ Project Structure
```
ML-project/
│
├── app.py                  # Flask web application entry point
├── setup.py                # Package setup
├── requirements.txt        # Python dependencies
│
├── src/
│   ├── pipeline/
│   │   ├── predict_pipeline.py   # Inference pipeline (CustomData + PredictPipeline)
│   │   └── train_pipeline.py     # Training orchestration
│   ├── components/
│   │   ├── data_ingestion.py     # Load and split dataset
│   │   ├── data_transformation.py# Preprocessing (scaling, encoding)
│   │   └── model_trainer.py      # Model training and evaluation
│   ├── exception.py              # Custom exception handling
│   ├── logger.py                 # Logging setup
│   └── utils.py                  # Helper functions
│
├── notebook/               # Jupyter notebooks for EDA and experimentation
├── artifacts/              # Saved models and preprocessor objects
├── catboost_info/          # CatBoost training metadata
└── templates/
    └── home.html           # Frontend HTML form
```
---

✨ Features
Accepts 7 student inputs through a web form
Preprocesses data using `StandardScaler` and encoding pipelines
Predicts math score using a trained ML model
Clean, modular code with separate training and prediction pipelines
Custom logging and exception handling throughout
---
🤖 Models Used
The project trains and evaluates multiple regression models:
Random Forest Regressor
Decision Tree Regressor
Gradient Boosting Regressor
Linear Regression
XGBoost Regressor
CatBoost Regressor
AdaBoost Regressor
The best-performing model is saved to `artifacts/` and used for predictions.

📥 Input Features
Feature	Description
`gender`	male / female
`race_ethnicity`	Group A / B / C / D / E
`parental_level_of_education`	e.g., bachelor's degree, some college
`lunch`	standard / free or reduced
`test_preparation_course`	completed / none
`reading_score`	Numeric (0–100)
`writing_score`	Numeric (0–100)
Output: Predicted math score (rounded to 2 decimal places)
---

🚀 Getting Started
1. Clone the Repository
```bash
git clone https://github.com/suhanisaxe14-prog/ML-project.git
cd ML-project
```
2. Install Dependencies
```bash
pip install -r requirements.txt
```
3. Train the Model
```bash
python src/pipeline/train_pipeline.py
```
This will ingest data, preprocess it, train all models, and save the best one along with the preprocessor to the `artifacts/` folder.
4. Run the Web App
```bash
python app.py
```
Open your browser and go to `http://localhost:5000`
---
🛠️ Tech Stack
Category	Tools
Language	Python 3
ML Libraries	scikit-learn, XGBoost, CatBoost
Data Handling	pandas, numpy
Visualization	matplotlib, seaborn
Web Framework	Flask
Serialization	dill
---






