# Obesity Level Prediction

A machine learning project that predicts **obesity categories** based on health measurements and lifestyle-related features.  
This project explores the dataset through visualization, prepares the data for modelling, and compares **Logistic Regression** and **Random Forest** to identify the better-performing model.

---

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## Project Goals

- Explore and understand the obesity dataset
- Visualize patterns in health and lifestyle features
- Preprocess categorical and numeric variables
- Build and compare classification models
- Select the most suitable model for obesity level prediction

---

## Dataset Overview

The dataset contains demographic, physical, and behavioural features related to obesity, including:

- Gender
- Age
- Height
- Weight
- Family history with overweight
- Eating habits
- Water consumption
- Physical activity
- Technology use time
- Transportation mode

The target variable is:

- `NObeyesdad` — obesity category label

### Target Classes

- Insufficient_Weight
- Normal_Weight
- Overweight_Level_I
- Overweight_Level_II
- Obesity_Type_I
- Obesity_Type_II
- Obesity_Type_III

---

## Project Structure

1. Read the dataset
2. Analyse and visualize the data
3. Organise the data for modelling
4. Implement prediction models
5. Train prediction models
6. Test prediction models and show results
7. Compare the models and choose the best one
8. Provide recommendations
9. Reflect on learning outcomes

---

## Data Analysis and Visualisation

The project includes several visualisation steps to better understand the dataset:

- Distribution plots for categorical features
- Correlation heatmap for feature relationships
- Boxplots of Age, Height, and Weight by obesity category

These visualisations help identify important patterns and support later modelling decisions.

---

## Data Preprocessing

Before training the models, the data was prepared using the following steps:

- Encoded the target variable (`NObeyesdad`) into numeric labels
- Split the dataset into training and testing sets using an 80/20 ratio
- Applied **one-hot encoding** to categorical features
- Applied **standardization** to numeric features
- Combined processed numeric and categorical features into final model inputs

### Feature Groups

**Categorical features**
- Gender
- family_history_with_overweight
- FAVC
- CAEC
- SMOKE
- SCC
- CALC
- MTRANS

**Numeric features**
- Age
- Height
- Weight
- FCVC
- NCP
- CH2O
- FAF
- TUE

---

## Models Used

### Logistic Regression
Used as a simple and interpretable **baseline model**.

### Random Forest
Used as a more flexible model capable of capturing **non-linear relationships** and interactions between variables.

---

## Model Performance

| Model | Accuracy |
|------|----------|
| Logistic Regression | 0.898 |
| Random Forest | 0.962 |

Random Forest achieved the best performance and was selected as the final model.

---

## Why Random Forest Was Chosen

Although Logistic Regression performed well, it was less effective in distinguishing between obesity categories that are close to each other, such as:

- Normal_Weight
- Overweight_Level_I
- Overweight_Level_II

This is likely because Logistic Regression uses linear decision boundaries, while obesity-related outcomes depend on more complex relationships among features such as **weight, height, eating habits, and physical activity**.

Random Forest performed better because it can:

- model non-linear relationships
- capture feature interactions more effectively
- classify neighbouring and extreme categories more accurately

In addition to higher accuracy, Random Forest also showed stronger performance in **precision, recall, and F1-score**.

---

## Key Evaluation Metrics

- **Accuracy**: overall proportion of correct predictions
- **Precision**: proportion of correct predictions among all predicted instances of a class
- **Recall**: proportion of correctly identified instances among all actual instances of a class
- **F1-score**: harmonic mean of precision and recall

These metrics are important because this is a **multi-class classification problem**, and accuracy alone does not fully describe model performance.

---

## Recommendations

Based on the dataset and model analysis, the following health-related recommendations can be made:

- Maintain a balanced diet
- Eat regular meals
- Stay hydrated
- Be physically active
- Reduce sedentary behaviour
- Moderate alcohol consumption
- Monitor weight trends, especially for people with a family history of overweight

Possible public health actions include:

- improving access to affordable healthy food
- supporting physical activity through community and urban planning
- increasing awareness of healthy lifestyle habits

---

## Limitations

- BMI was not explicitly created as a feature, even though it is strongly related to obesity classification
- Some classes are close to each other, making classification more challenging
- The project only compares two models; future work could include more advanced models

---

## Future Improvements

- Add a **BMI feature**
- Tune Random Forest hyperparameters
- Compare with more models such as Decision Tree, KNN, or XGBoost
- Perform cross-validation for more robust evaluation
- Add feature importance analysis

---

## What I Learned

Through this project, I learned how to:

- explore a dataset before modelling
- preprocess categorical and numeric data properly
- compare machine learning models using multiple evaluation metrics
- interpret model results in a meaningful way
- connect technical findings to health-related recommendations

This project also improved my understanding of how machine learning can be applied to real-world classification problems.

---

## Running the Project

1. Clone the repository
2. Install dependencies
3. Open the Jupyter Notebook
4. Run all cells in order

Example:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook
jupyter notebook
