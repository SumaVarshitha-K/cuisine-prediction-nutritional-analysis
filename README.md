# Cuisine Prediction and Nutritional Analysis of Global Recipes Using Machine Learning

## Project Overview

This project uses machine learning to predict the cuisine category of a recipe based on its ingredients and performs exploratory nutritional analysis across predicted cuisine categories.

The project implements and compares two classification algorithms, Logistic Regression and Linear Support Vector Machine (Linear SVM), using TF-IDF feature extraction. The best-performing model is then used to predict cuisine categories for recipes from a separate dataset. Nutritional information is analyzed and visualized using Python.

## Objectives

- Preprocess recipe datasets and clean ingredient information.
- Convert recipe ingredients into numerical features using TF-IDF.
- Train and compare Logistic Regression and Linear SVM classifiers.
- Tune model hyperparameters using GridSearchCV.
- Evaluate models using accuracy, weighted precision, weighted recall, and a confusion matrix.
- Predict cuisine categories for recipes from the Food.com dataset.
- Compare nutritional characteristics across predicted cuisine categories.
- Visualize model performance and nutritional patterns.

## Datasets Used

### 1. What's Cooking Dataset

- Source: [Kaggle – What's Cooking?](https://www.kaggle.com/competitions/whats-cooking)
- Number of recipes after preprocessing: 39,774
- Number of cuisine categories: 20
- Main features: Recipe ID, cuisine, and ingredients.
- Purpose: Training and testing the classification models.

### 2. Food.com Recipes and User Interactions Dataset

- Source: [Kaggle – Food.com Recipes and User Interactions](https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions)
- Number of recipes after preprocessing: 231,637
- Sample used for analysis: 50,000 recipes
- Main features: Recipe ID, recipe name, ingredients, and nutritional information.
- Purpose: Cuisine prediction and nutritional analysis.

**Note:** The cuisine categories assigned to Food.com recipes are model predictions, not verified ground-truth labels.

## Technologies Used

- Python
- Google Colab
- Pandas
- Scikit-learn
- Matplotlib
- TF-IDF Vectorization
- Logistic Regression
- Linear Support Vector Machine (Linear SVM)
- GridSearchCV

## Methodology

The project follows these steps:

1. **Data Loading:** Load the What's Cooking and Food.com datasets.
2. **Data Preprocessing:** Remove duplicate records, handle missing information, and clean ingredient lists.
3. **Feature Extraction:** Convert ingredient text into numerical features using TF-IDF with a maximum of 5,000 features and unigram/bigram representations.
4. **Train-Test Split:** Split the labelled What's Cooking dataset into 80% training data and 20% testing data using stratified sampling.
5. **Model Training:** Train Logistic Regression and Linear SVM classifiers.
6. **Hyperparameter Tuning:** Use GridSearchCV with three-fold cross-validation to identify suitable values of the regularization parameter C.
7. **Model Evaluation:** Compare accuracy, weighted precision, weighted recall, and the confusion matrix.
8. **Cuisine Prediction:** Apply the selected Linear SVM model to a sample of 50,000 Food.com recipes.
9. **Nutritional Analysis:** Calculate average nutritional values for each predicted cuisine category.
10. **Visualization:** Create charts to compare model performance and nutritional characteristics.

## Model Performance

The tuned models were evaluated on the held-out test dataset.

| Model | Best C | Test Accuracy | Weighted Precision | Weighted Recall |
|---|---:|---:|---:|---:|
| Logistic Regression | 10 | 76.40% | 76.13% | 76.40% |
| Linear SVM | 1 | 77.16% | 76.77% | 77.16% |

### Hyperparameter Tuning Results

| Model | Best C | Best Cross-Validation Accuracy |
|---|---:|---:|
| Logistic Regression | 10 | 76.71% |
| Linear SVM | 1 | 77.00% |

**Best-performing model:** Tuned Linear SVM, with a test accuracy of **77.16%**.

## Cuisine Prediction Results

The tuned Linear SVM model was used to predict cuisine categories for 50,000 sampled Food.com recipes.

The five most frequent predicted categories were:

| Predicted Cuisine | Number of Recipes |
|---|---:|
| Southern US | 12,980 |
| Italian | 11,111 |
| Mexican | 6,207 |
| French | 4,031 |
| Chinese | 1,839 |

These figures represent predicted categories and should not be interpreted as verified cuisine labels.

## Nutritional Analysis

The project analyzes the following nutritional variables:

- Calories
- Total fat
- Sugar
- Sodium
- Protein
- Saturated fat
- Carbohydrates

The analysis includes:

- Average calorie comparison across predicted cuisine categories.
- Protein and sugar Daily Value percentage comparison.
- Sodium and total fat Daily Value percentage comparison.
- A nutritional summary grouped by predicted cuisine.

### Visualizations

The project generates the following visualizations:

1. Model accuracy comparison.
2. Confusion matrix for cuisine classification.
3. Average calories by predicted cuisine.
4. Protein and sugar Daily Value percentage comparison.
5. Sodium and total fat Daily Value percentage comparison.

## Key Findings

- TF-IDF provides a numerical representation of recipe ingredients suitable for text classification.
- Both Logistic Regression and Linear SVM achieved test accuracy of approximately 77%.
- Tuned Linear SVM achieved the highest test accuracy at 77.16%.
- The selected model predicted all 20 cuisine categories in the 50,000-recipe Food.com sample.
- Nutritional information can be grouped and explored using the predicted cuisine categories.
- Reliable cuisine labels and standardized nutritional measurements are important for drawing stronger conclusions.

## Limitations

- The best model achieved 77.16% test accuracy, so some recipes were incorrectly classified.
- Food.com cuisine categories were predicted rather than verified.
- Differences between the two datasets may affect predictions on Food.com recipes.
- Nutritional values other than calories are represented as percentages of Daily Value, not grams or milligrams.
- Calorie averages are calculated per recipe, not per serving.
- Nutritional comparisons are exploratory and do not establish that one cuisine is healthier than another.

## Future Enhancements

- Experiment with additional classification algorithms.
- Expand the hyperparameter search.
- Improve ingredient normalization and text processing.
- Use verified cuisine labels for nutritional comparisons.
- Compare nutritional values per serving or per 100 grams.
- Develop an interactive web application for recipe cuisine prediction.
- Add recipe recommendations based on available ingredients.

## How to Run the Project

1. Download or clone this repository.
2. Download the required datasets from the Kaggle sources listed above.
3. Open `Cuisine_Prediction.ipynb` in Google Colab.
4. Upload the datasets to Colab or configure the notebook to access them.
5. Run the notebook cells in order.
6. Review the classification metrics, confusion matrix, predicted cuisine distribution, and nutritional charts.

The notebook may require minor path changes depending on where the datasets are stored.

## Project Structure

```text
cuisine-prediction-nutritional-analysis/
│
├── Cuisine_Prediction.ipynb
├── Project_Report.pdf
├── model_comparison.csv
├── cuisine_classification_report.csv
├── nutrition_summary_by_cuisine.csv
├── README.md
└── images/
    ├── model_accuracy_comparison.png
    ├── confusion_matrix.png
    ├── average_calories_by_cuisine.png
    ├── protein_sugar_comparison.png
    └── sodium_fat_comparison.png
```

*The filenames above are suggested names. Include only files that actually exist in your repository.*

## Conclusion

This project demonstrates how machine learning can be applied to recipe ingredient data to predict cuisine categories and support exploratory nutritional analysis. By combining TF-IDF, Logistic Regression, Linear SVM, hyperparameter tuning, and data visualization, the project builds a complete workflow for recipe classification and nutritional comparison.

The tuned Linear SVM achieved 77.16% test accuracy and was selected for cuisine prediction on the Food.com sample. The project also highlights the importance of data quality, reliable labels, and careful interpretation of nutritional information.

## References

1. [Kaggle – What's Cooking?](https://www.kaggle.com/competitions/whats-cooking)
2. [Kaggle – Food.com Recipes and User Interactions](https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions)
3. [Scikit-learn Documentation](https://scikit-learn.org/)
4. [TF-IDF Vectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html)
5. [Logistic Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html)
6. [LinearSVC](https://scikit-learn.org/stable/modules/generated/sklearn.svm.LinearSVC.html)
7. [GridSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html)

---

**Developed using Python, Google Colab, Pandas, Scikit-learn, and Matplotlib.**
