Student Performance Prediction
An end-to-end machine learning project that predicts students' math scores from demographic, socioeconomic, and academic features. The project is organized as a modular Python package rather than a single notebook, with separate components for data ingestion, preprocessing, model training, logging, exception handling, and model persistence.
Project Overview
The objective is to predict math_score using:
- Gender
- Race/ethnicity
- Parental level of education
- Lunch type
- Test preparation course
- Reading score
- Writing score
The project uses the Students Performance in Exams dataset and follows a reproducible machine learning workflow from raw data ingestion through model selection and serialization.
Key Features
- Exploratory Data Analysis using Pandas, Matplotlib, and Seaborn
- Train/test data ingestion and splitting
- Separate numerical and categorical preprocessing pipelines
- Missing-value handling with SimpleImputer
- Numerical feature scaling with StandardScaler
- Categorical encoding with OneHotEncoder
- Feature transformation using ColumnTransformer
- Comparison of multiple regression algorithms
- Hyperparameter tuning with GridSearchCV
- Model selection based on test-set R²
- Model serialization with Pickle
- Reusable utility functions for model evaluation and object persistence
- Custom exception handling
- Application logging
- Python package structure using setup.py
Models
The training pipeline evaluates:
- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor
- AdaBoost Regressor
- XGBoost Regressor
- CatBoost Regressor
Hyperparameters are searched with cross-validation using GridSearchCV for applicable models.
Results
The exploratory model-training notebook reports a test-set R² of approximately 0.88 for the strongest simple linear/ridge models.
For example, the notebook reports:
- Linear Regression — R²: 0.8804
- Ridge Regression — R²: 0.8806
- Linear Regression — RMSE: 5.3940
- Linear Regression — MAE: 4.2148
Results can vary with library versions and model configuration.
Project Structure
MLProject1/
│
├── notebook/
│   ├── EDA_studentPerformance.ipynb
│   ├── ModelTraining.ipynb
│   └── data/
│       └── stud.csv
│
├── src/
│   ├── components/
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   └── model_trainer.py
│   │
│   ├── pipeline/
│   ├── exception.py
│   ├── logger.py
│   └── utils.py
│
├── requirements.txt
├── setup.py
└── README.md
Workflow
Raw Dataset
     │
     ▼
Data Ingestion
     │
     ├── Raw data
     ├── Train split
     └── Test split
     │
     ▼
Data Transformation
     │
     ├── Numerical pipeline
     │   ├── Median imputation
     │   └── Standard scaling
     │
     └── Categorical pipeline
         ├── Most-frequent imputation
         ├── One-hot encoding
         └── Scaling
     │
     ▼
Model Training
     │
     ├── Multiple regressors
     ├── GridSearchCV
     └── Model comparison
     │
     ▼
Best Model
     │
     └── Serialized with Pickle
Installation
Clone the repository:
git clone https://github.com/developrishu-cell/MLProject1.git
cd MLProject1
Create and activate a virtual environment:
python -m venv venv
Windows:
venv\Scripts\activate
Install dependencies:
pip install -r requirements.txt
The project also supports editable installation through:
pip install -e .
Running the Project
The notebook workflow can be explored through:
- notebook/EDA_studentPerformance.ipynb
- notebook/ModelTraining.ipynb
The modular components under src/ provide the reusable project implementation for ingestion, transformation, training, logging, exception handling, and model persistence.
Technologies
Python | Pandas | NumPy | Scikit-learn | XGBoost | CatBoost | Matplotlib | Seaborn | Flask | Git
Learning Outcomes
This project demonstrates practical understanding of:
- End-to-end machine learning project structure
- Regression model development
- Data preprocessing
- Feature engineering and transformation
- Model comparison and hyperparameter tuning
- Modular Python development
- Logging and custom exception handling
- Model serialization and reuse
Author
Rishu Ranjan Choudhary
GitHub: https://github.com/developrishu-cell
