# IMDb Movie Review Sentiment Analysis Project

For this project, I was tasked with building a model to classify IMDb movie reviews as either positive or negative. My goal was to go beyond a basic model and implement a more sophisticated pipeline to achieve high accuracy and demonstrate a strong understanding of NLP fundamentals.

## My Approach & Methodology

I followed a structured approach, focusing heavily on careful text preprocessing and intelligent feature engineering before training any models. The key stages were:

1.  **Advanced Text Preprocessing:** Cleaning the raw text to prepare it for the model.
2.  **TF-IDF Vectorization:** Converting the cleaned text into meaningful numerical features.
3.  **Model Training and Evaluation:** Training two powerful models and selecting the best one.

---

### 1. Advanced Preprocessing - Getting the Text Ready

Raw text from the internet is messy. My first and most important step was to build a robust cleaning function to normalize the reviews. This function performed several key tasks:

* **Standardization:** Converted all text to lowercase and removed distracting HTML tags (`<br />`) and punctuation.
* **Stop Word Removal:** I removed common English "stop words" (like 'the', 'a', 'in', 'is') because they don't carry much sentiment and can add noise, making it harder for the model to find the important signals.
* **Lemmatization:** Instead of just chopping off the ends of words (stemming), I used lemmatization to convert words to their true root form (e.g., 'studies' and 'studying' both become 'study'). This helps the model understand that different forms of a word have the same core meaning, leading to a more accurate feature set.

### 2. Feature Engineering - Turning Words into Numbers with TF-IDF

A model can't understand words, so I needed to convert the cleaned reviews into numerical features. For this, I chose the **TF-IDF (Term Frequency-Inverse Document Frequency)** method over a simple word count for a couple of important reasons:

* **It's Smarter Than a Simple Count:** TF-IDF gives a higher score (weight) to words that are important to a *specific* review but are rare in *all* other reviews. This is great for identifying words that are most likely to indicate a strong positive or negative sentiment (like "masterpiece" or "awful").
* **It Captures Context with N-grams:** I also configured the vectorizer to look at pairs of words (bigrams), not just single words. This is crucial for capturing context, like the phrase **"not good,"** which has a completely different meaning than the words "not" and "good" on their own.

### 3. Model Training & Final Results

With the data prepared, I trained two different but powerful classification models: **Logistic Regression** and a **Linear Support Vector Classifier (SVC)**.

After training on 80% of the data, I evaluated both models on the remaining 20% of unseen data to get an honest measure of their performance.
### 4. Project structure 

MIC_sentiment_analysis_v/
├── data/                          # Folder to store the IMDb dataset
├── notebooks/                     # Jupyter notebooks for experimentation
│   └── MIC_sentiment_analysis.ipynb  # Main analysis notebook
├── src/                           # Python scripts for modular code (optional)
│   ├── preprocessing.py           # Text cleaning and preprocessing functions
│   ├── model.py                   # Model training and evaluation logic
│   └── utils.py                   # Helper functions
├── requirements.txt               # Python dependencies
├── LICENSE                        # MIT License
└── README.md                      # Project documentation

### 5. Tech Stack
1.Python 3.10+
2.scikit-learn    
3.NLTK
4.Pandas
5.NumPy
6.Jupyter Notebook

### 6. clone the repo

git clone https://github.com/srisaihariharan/MIC_sentiment_analysis_v.git
cd MIC_sentiment_analysis_v

### 7. Results

| Model               | Accuracy  | Precision | Recall | F1-Score |
|--------------------|-----------|-----------|--------|----------|
| Logistic Regression| 87.98%    | 88.10%    | 87.50% | 87.80%   |
| Linear SVC         | 86.45%    | 86.70%    | 86.20% | 86.45%   |

**The Logistic Regression model was the top performer, achieving a final accuracy of 87.98%.**
---
### How to Run the Code

1.  The entire process is contained in the `IMDB_Sentiment_Analysis.ipynb` notebook.
2.  To run it, open the notebook in a Python environment like Google Colab.
3.  Upload the `IMDB Dataset.csv` file to the environment.
4.  Run all the cells in the notebook from top to bottom. The process will print its progress and the final accuracy results at the end.
### Performance Visualization

To better understand the model's performance, I generated a confusion matrix, which shows the breakdown of correct and incorrect predictions and attached the pnj file.


<img width="649" height="547" alt="image" src="https://github.com/user-attachments/assets/ab26f93f-8f01-4363-9af2-7f88b11a2144" />

---
**Note: If the notebook below does not render correctly on GitHub, please [view it on nbviewer](https://nbviewer.org/github/srisaihariharan/MIC_sentiment_analysis_v/tree/main/)).**

---
## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

