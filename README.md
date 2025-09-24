# IMDb Movie Review Sentiment Analysis
This project aims to classify movie reviews from the IMDb dataset as either positive or negative by using the two coloumns given in the dataset: review(text) and sentiment(label)

## Dataset
The dataset used is the IMDb Movie Review Dataset, containing 50,000 reviews labeled as 'positive' or 'negative'.

## Preprocessing Steps

The following preprocessing steps were applied to the text data before training the model:
1.  **Label Encoding**: The 'sentiment' column was converted from text ('positive'/'negative') to numerical format (1/0).
2.  **Lowercase Conversion**: All text was converted to lowercase to ensure uniformity.
3.  **HTML Tag Removal**: HTML tags like `<br />` were removed from the reviews.
4.  **Punctuation Removal**: All punctuation and special characters were removed, keeping only alphabetic characters and spaces.
5.  **Text Vectorization**: The cleaned text was converted into numerical vectors using the Bag-of-Words model with `CountVectorizer`.

## Model Used

A **Logistic Regression** model was trained for the classification task.

## Results

The model was evaluated on a test set (20% of the data) and achieved an accuracy of **88.45%**.

## How to Run the Code

1.  Make sure you have Python and Jupyter Notebook installed.
2.  Install the required libraries: `pip install pandas scikit-learn`.
3.  Download the `IMDB Dataset.csv` and place it in the same directory.
4.  Run the Jupyter Notebook `sentiment_analysis.ipynb`.
