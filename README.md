# Twitter Sentiment Analysis (Sentiment140)

This project builds a **binary sentiment analysis model** on the **Sentiment140** Twitter dataset from Kaggle.  
Tweets are classified as either:

- `0` → Negative  
- `1` → Positive  

The workflow uses classic NLP preprocessing with a **Logistic Regression** classifier trained on bag-of-words features.

---

##  Dataset

- Source: [Sentiment140 Dataset (Kaggle)](https://www.kaggle.com/datasets/kazanova/sentiment140)
- Loaded via `kagglehub` inside the notebook.
- Original labels:  
  - `0` = negative  
  - `4` = positive  

In this project, label `4` is converted to `1` → **clean binary labels {0, 1}.**

Main columns used:

- `target` – sentiment label (0 or 1)  
- `text` – tweet content  

---

## 🔧 Pipeline Overview

1. **Load dataset** with `pandas`.
2. **Relabel** target values (`4 → 1`).
3. **Text preprocessing**:
   - Remove non-alphabetic characters with regex  
   - Convert to lowercase  
   - Remove English stopwords (NLTK)  
   - Apply Porter stemming (`PorterStemmer`)
4. **Vectorisation**:
   - `CountVectorizer` to convert text into sparse feature vectors.
5. **Train/Test Split**:
   - `train_test_split`, `test_size=0.2`, stratified on labels.
6. **Model**:
   - `LogisticRegression(max_iter=1000)` from scikit-learn.
7. **Evaluation**:
   - Accuracy on training and test sets.
8. **Saving Artifacts**:
   - Model → `trained_model.sav` (pickle)  
   - Vectorizer → `vectorizer.pkl` (pickle)

---

##  Requirements

Install all dependencies with:

```bash
pip install -r requirements.txt

(Notice the closing triple backticks.)

---


```markdown
##  How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/vic219/twitter_sentiment_analysis.git
   cd twitter_sentiment_analysis
2. Install dependencies:

pip install -r requirements.txt


3. Open Twitter_sentiment_analysis.ipynb in Jupyter, VS Code, or Google Colab.


4. Run all cells in order.
The notebook will:

Load and preprocess the Sentiment140 dataset

Train the Logistic Regression model

Save:

trained_model.sav

vectorizer.pkl

