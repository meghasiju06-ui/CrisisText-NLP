# CrisisText-NLP

NLP-based classification of disaster-related tweets into humanitarian categories using TF-IDF and machine learning.

## 1. Project Overview

CrisisText is a Natural Language Processing (NLP) project that classifies disaster-related social-media posts into different humanitarian information categories.

During natural disasters such as hurricanes, earthquakes, floods, and wildfires, social-media platforms contain a large amount of information. Manually organizing this information can be time-consuming.

This project develops a machine-learning-based text classification system that takes a disaster-related tweet as input and predicts its humanitarian category.

The system is developed as a prototype decision-support tool for organizing disaster-related information. It is not intended to replace emergency authorities or guarantee the correctness of emergency information.

## 2. Objectives

- Identify a socially relevant NLP problem related to disaster response.
- Use a publicly available disaster-related social-media dataset.
- Clean and preprocess disaster-related tweet text.
- Convert text into numerical features using TF-IDF.
- Implement Multinomial Naive Bayes.
- Implement Logistic Regression.
- Compare the performance of both models.
- Select the better-performing model.
- Evaluate the final model using accuracy, precision, recall, F1-score, and a confusion matrix.
- Test the model using new, unseen text.

## 3. Dataset

### Dataset Name
CrisisMMD v2.0

### Source
CrisisNLP / Qatar Computing Research Institute (QCRI)

The dataset contains disaster-related Twitter posts and associated images collected during major natural disasters.

For this project, only the textual component of the dataset is used.

### Input
`tweet_text`

### Target
`label_text`

### Final Categories

The original humanitarian categories were merged into five broader categories:

1. Affected Individuals
2. Infrastructure and Utility Damage
3. Not Humanitarian
4. Other Relevant Information
5. Rescue, Volunteering or Donation Effort

### Dataset Split

| Dataset | Records |
|---|---:|
| Training | 11,584 |
| Development | 2,237 |
| Testing | 2,237 |
| Total | 16,058 |

## 4. Methodology

The project follows a text classification pipeline.

First, the dataset is loaded and related humanitarian categories are merged into five broader categories. Duplicate tweet IDs are removed to improve data quality.

The tweet text is then preprocessed by converting it to lowercase and removing URLs, user mentions, retweet indicators, hashtags, punctuation, and unnecessary characters.

After preprocessing, TF-IDF (Term Frequency-Inverse Document Frequency) is used to convert the tweets into numerical features. Both unigrams and bigrams are considered, with a maximum of 10,000 features.

Two machine-learning algorithms are trained and compared:

- Multinomial Naive Bayes
- Logistic Regression

Logistic Regression performs better on the development dataset and is selected as the final model.

## 5. Technologies and Libraries

### Programming Language
- Python

### Libraries
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- SciPy
- Regular Expressions (`re`)

## 6. Model Comparison

| Model | Development Accuracy |
|---|---:|
| Multinomial Naive Bayes | 61.6% |
| Logistic Regression | 65.4% |

Logistic Regression achieved 3.8 percentage points higher accuracy than Multinomial Naive Bayes and was therefore selected as the final model.

## 7. Final Results

The selected Logistic Regression model was trained using the combined training and development datasets.

### Final Test Accuracy

**64.1%**

### Evaluation Metrics

The final model was evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

The final model achieved:

- **Accuracy:** 64.1%
- **Weighted F1-score:** 0.64
- **Macro F1-score:** 0.61

## 8. Sample Predictions

The trained model can classify new disaster-related text.

Example:

| Input | Predicted Category |
|---|---|
| Many families have lost their homes after the hurricane. | Affected Individuals |
| Volunteers are collecting food and donations for flood victims. | Rescue/Volunteering/Donation Effort |
| The earthquake damaged roads and several buildings. | Infrastructure and Utility Damage |
| Authorities shared information about the ongoing wildfire. | Not Humanitarian |
| I watched a video about the storm on social media. | Other Relevant Information |

## 9. Project Structure

```text
CrisisText-NLP/
│
├── README.md
├── source_code.py
├── requirements.txt
│
├── dataset/
│   └── README.md
│
├── screenshots/
│   ├── class_distribution.png
│   ├── preprocessing_example.png
│   ├── model_comparison.png
│   ├── confusion_matrix.png
│   └── sample_predictions.png
│
└── report/
    └── CrisisText_Report.pdf
