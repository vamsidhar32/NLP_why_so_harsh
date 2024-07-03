# Problem Statement
This project addresses the challenge of identifying and classifying comments into multiple categories of offensive language. These categories include "harsh," "extremely harsh," "vulgar," "threatening," "disrespectful," and "targeted hate." The goal is to develop an accurate model that can assist in moderating online content and maintaining a positive and respectful environment.

## Procedure
To prepare the dataset for analysis, several pre-processing steps were performed:

+ Expanding Contractions: Replacing contractions with their expanded forms.
+ Handling Emoticons: Converting emoticons to descriptive words.
+ Removing Special Characters: Discarding punctuation and other non-informative characters.
+ Removing Stop Words: Eliminating common words that do not contribute to the tone of the comment.
+ Lemmatization: Reducing words to their base forms and tagging parts of speech.

For feature extraction, TF-IDF vectorizers were used to convert the cleaned text into numerical representations. This included both word-level and character-level features to capture the order and frequency of terms.

Multiple models were evaluated for their effectiveness in multi-label classification, including:

+ Naive Bayes
+ Logistic Regression
+ Random Forest
+ Chain Classifiers
+ Ridge Classifier
+ Support Vector Machines

Hyperparameter tuning and cross-validation were applied to optimize model performance. Among the tested models, Logistic Regression showed the best results, especially when fine-tuned using grid search and cross-validation techniques.

## Results
The best-performing model was Logistic Regression, achieving an accuracy of 0.984 after grid search optimization. This model proved highly effective in classifying offensive comments, making it a suitable choice for real-world moderation systems.

### Model Performance

| Model                           | Accuracy |
|---------------------------------|----------|
| Logistic Regression             | 0.984    |
| Naive Bayes                     | 0.94     |
| Random Forest                   | 0.969    |
| Ridge Classifier                | 0.683    |
| Naive Bayes Chain               | 0.941    |
| Ridge Classifier (Grid Search)  | 0.611    |
| Ridge Regression                | 0.981    |

### Tuning Best Model

| Model Variation                             | Accuracy |
|---------------------------------------------|----------|
| Logistic Regression (StratifiedKFold)       | 0.98111  |
| Logistic Regression (Grid Search)           | 0.98412  |
| Logistic Regression (Chain Classifier)      | 0.97933  |
| Logistic Regression (solver = liblinear, C=2) | 0.98411  |
| Logistic Regression (Updated Max Features)  | 0.98414  |
