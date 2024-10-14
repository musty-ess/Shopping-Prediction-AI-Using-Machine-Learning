# Shopping Prediction AI Using Machine Learning

## Project Overview

This project is an AI model designed to predict whether customers on an online shopping website will complete a purchase. The goal is to use machine learning, specifically a k-nearest neighbors (KNN) classifier, to analyze user behavior and predict their purchasing intent. The model could be used by online shopping websites to display targeted content, such as offering discounts to users who are less likely to make a purchase.

## Features

The classifier uses various features from user sessions, such as:
- Number of pages visited (administrative, informational, product-related pages)
- Time spent on each page
- Bounce rates, exit rates, and page values (from Google Analytics)
- Special days (e.g., proximity to holidays like Valentine's Day)
- User attributes (operating system, browser, traffic source, returning visitor status, weekend browsing)
- And more...

Based on this data, the classifier predicts whether a user will complete a purchase.

## File Structure

- `shopping.py`: Main script that loads data, trains the model, and evaluates predictions.
- `shopping.csv`: Dataset containing session data of around 12,000 online users.

## Key Functions Implemented

### `load_data(filename)`
- Loads the shopping data from `shopping.csv`.
- Converts the features into a format suitable for the k-nearest neighbors algorithm.
- Returns two lists: `evidence` (features for each user session) and `labels` (whether or not the user made a purchase).

### `train_model(evidence, labels)`
- Trains a KNN classifier (k = 1) using the provided `evidence` and `labels`.
- Returns a trained model that can be used to predict whether a user will complete a purchase.

### `evaluate(labels, predictions)`
- Evaluates the performance of the model.
- Returns two metrics:
  - **Sensitivity**: True positive rate (correctly identified purchases).
  - **Specificity**: True negative rate (correctly identified non-purchases).

## Installation
1. **clone the repo**: `git clone https://github.com/musty-ess/Shopping-Prediction-AI-Using-Machine-Learning.git`
2. **Install necessary dependencies**: `pip install scikit-learn`

## Usage

To run the program, use the following command: `python shopping.py shopping.csv`

The model will load the dataset, train on a portion of it, and then make predictions on the test set. The results, including the sensitivity and specificity, will be displayed in the terminal.

## Sample Output

```python
python shopping.py shopping.csv
Correct: 4088
Incorrect: 844
True Positive Rate: 41.02%
True Negative Rate: 90.55%
```
