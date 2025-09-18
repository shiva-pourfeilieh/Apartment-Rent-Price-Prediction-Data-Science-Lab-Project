# Apartment-Rent-Price-Prediction-Data-Science-Lab-Project
Machine Learning project for predicting apartment rental prices using regression models. Includes preprocessing, feature engineering, and model evaluation with MAE metric.


**Introduction**

This project was developed as part of the Data Science Lab course at Politecnico di Torino.
The main objective is to predict the monthly rental price of apartments in the U.S. housing market.
Reliable rent price predictions can help:
	•	Tenants and landlords find fair prices,
	•	Investors evaluate profitability,
	•	Urban planners address housing affordability challenges.

The project follows the standard machine learning pipeline: data preprocessing → feature engineering → model training → evaluation → results.

⸻

**Dataset**

The dataset contains ~100,000 rental listings collected from different real-estate and classified ads websites in the U.S.

Main features include:
	•	Numerical: square footage, number of bedrooms, number of bathrooms, latitude, longitude.
	•	Categorical: city, state, amenities, pets allowed, room type.
	•	Textual: title and description of the listing.
	•	Target variable: rental price (USD).

The dataset was divided into:
	•	Development set – with price labels (used for training & validation).
	•	Evaluation set – without price labels (used for final testing).

⸻

**Methods**

The workflow was structured as follows:

1. Preprocessing
	•	Removed duplicates and irrelevant columns.
	•	Handled missing values (imputation or dropping when necessary).
	•	One-hot encoding for categorical variables (e.g., room type, city).
	•	Normalization/standardization for numerical features where required.

2. Exploratory Data Analysis (EDA)
	•	Checked feature distributions and correlations with price.
	•	Verified skewness and outliers in the price variable.
	•	Observed geographic trends using latitude/longitude.

3. Feature Engineering
	•	Derived new features from existing ones (e.g., log-transform of price and square footage).
	•	Explored importance of location by combining city/state with geo-coordinates.
	•	Considered textual features (title/description) for future improvements.

4. Model Training & Testing

We tested several regression models:
	•	Linear Regression → baseline model, interpretable but underfitted.
	•	Random Forest Regressor → handled categorical + numerical mix well, strong baseline.
	•	Gradient Boosting (XGBoost/LightGBM) → tested to capture complex non-linear relations.

5. Hyperparameter Tuning
	•	Used Grid Search + Cross Validation (k=5).
	•	Tuned parameters such as depth, number of trees, learning rate.

⸻

**Experiments & Results**
	•	Baseline (Linear Regression): Poor performance due to non-linear relationships.
	•	Random Forest: Improved MAE, good at handling high-dimensional categorical data.
	•	Gradient Boosting: Achieved the best overall performance with the lowest MAE.

**Evaluation Metric: Mean Absolute Error (MAE)**
	•	Final tuned model significantly reduced MAE compared to baseline.
	•	Location (latitude/longitude) and property size were the strongest predictors.

⸻

**Discussion**
	•	The project highlighted the strong influence of location and property size on rental prices.
	•	Some redundancy existed in features (e.g., neighborhoods vs geo-coordinates).
	•	Textual features (listing description) were not fully integrated but remain a promising extension.
	•	Feature engineering and careful preprocessing were crucial to improving performance.
