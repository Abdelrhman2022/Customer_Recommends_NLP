# Customer_Recommends_NLP
Create a machine-learning model pipeline. The objective is to predict whether a product is recommended by a customer based on their review.
The dataset includes numerical, categorical, and text data, requiring proper preprocessing.


## The Data

The dataset has been anonymized and cleaned of missing values.

There are 8 features for to use to predict whether a customer recommends or does
not recommend a product.
The `Recommended IND` column gives whether a customer recommends the product
where `1` is recommended and a `0` is not recommended.
This is your model's target/

The features can be summarized as the following:

- **Clothing ID**: Integer Categorical variable that refers to the specific piece being reviewed.
- **Age**: Positive Integer variable of the reviewers age.
- **Title**: String variable for the title of the review.
- **Review Text**: String variable for the review body.
- **Positive Feedback Count**: Positive Integer documenting the number of other customers who found this review positive.
- **Division Name**: Categorical name of the product high-level division.
- **Department Name**: Categorical name of the product department name.
- **Class Name**: Categorical name of the product class name.

The target:
- **Recommended IND**: Binary variable stating where the customer recommends the product where 1 is recommended, 0 is not recommended.

## **Data Loading & Exploration**

- **Data Loading:** Using `pandas` to load and inspect data (`df.info()`, `df.head()`).
- **Data Visualization:**  
  - Distribution of numerical features using `Seaborn` and `Matplotlib`.
  - Count plots for categorical variables.
  - Word cloud for text data insights.
  - Correlation heatmap for numerical features.

---

## **Feature Engineering**

- **Numerical Features:**  
  - Imputation with `SimpleImputer` (mean strategy).  
  - Scaling with `MinMaxScaler`.

- **Categorical Features:**  
  - Encoding with `OrdinalEncoder` and `OneHotEncoder`.  
  - Handling unknown values gracefully.

- **Text Processing:**  
  - Custom Transformers: `CountCharacter`, `PosExtractor`, `EntityExtractor`, `POSAndNERTransformer`.  
  - Text Preprocessing with `spaCy` and `TfidfVectorizer` for vectorization.

- **Pipeline Construction:**  
  - `Pipeline` and `ColumnTransformer` to unify preprocessing.  
  - `FeatureUnion` to combine multiple feature engineering steps seamlessly.

---

## **Modeling**

- **Model Choice:**  
  - `RandomForestClassifier` chosen for its robustness and performance on mixed data types.

- **Pipeline Integration:**  
  - End-to-end model pipeline using `make_pipeline` for preprocessing and modeling.  
  - Supports direct `.fit()` and `.predict()` operations.

- **Evaluation Metrics:**  
  - **Classification Metrics:** Accuracy, Precision, Recall.  
  - **Visualization:** Confusion matrix heatmap for detailed performance insights.

---

## **Hyperparameter Tuning**

- **RandomizedSearchCV:**  
  - Extensive parameter grid to fine-tune model performance.  
  - Cross-validation (`cv=5`) for robust hyperparameter selection.  
  - Key parameters tuned:  
    - `n_estimators`, `max_features`, `max_depth`.  
    - `min_samples_split`, `min_samples_leaf`, `criterion`.  

---

## **Next Steps**

- Further feature engineering for text data.
- Experimenting with different models and ensemble techniques.
- Improving hyperparameter tuning with `GridSearchCV` if needed.
- Deployment of the model pipeline using `Flask` or `Streamlit` for a user-friendly interface.

---

## **Dependencies**

- `pandas`, `numpy`, `matplotlib`, `seaborn`
- `scikit-learn`, `spaCy`, `wordcloud`
- `RandomForestClassifier`, `RandomizedSearchCV`

---
