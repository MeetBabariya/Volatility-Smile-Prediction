Volatility Curve Prediction

This project focuses on predicting the volatility smile/surface in options markets using machine learning–based imputation techniques. The objective is to estimate missing implied volatility (IV) values across different strikes and maturities, enabling accurate modeling of the volatility curve for use in pricing, trading, and risk management.

📂 Repository Structure

all_imputers.ipynb – Exploratory notebook comparing different imputation methods for handling missing IV data
best_submission.ipynb – Final pipeline with the selected model (ExtraTreesRegressor + IterativeImputer) to generate predictions
submission.csv – Final output file prepared in the required format for submission

🔍 Approach

Data Loading & Preprocessing
Used Kaggle competition dataset (train/test parquet files + sample submission)
Converted numerical data to float32 for memory efficiency

Feature Engineering

Predictors: X0–X41, underlying, and timestamp
Target variables: missing call_iv and put_iv values

Imputation Strategy

Implemented Iterative Imputer with an ExtraTreesRegressor (800 estimators, depth 35)
Trained iteratively until convergence to fill missing volatility values

Final Submission

Constructed the complete volatility curve across strike prices
Generated submission.csv with timestamp, call_iv_*, and put_iv_* columns

📊 Results

Successfully imputed missing volatility values with a robust ensemble method
Produced a complete volatility curve dataset ready for downstream modeling or option pricing applications
Demonstrated scalability to large datasets (12,000+ rows, 95 columns)

🛠️ Tech Stack

Python: Pandas, NumPy, Scikit-learn
Machine Learning: ExtraTreesRegressor, IterativeImputer
Visualization & Analysis: Jupyter Notebooks
