# Email/SMS Spam Detection with Machine Learning (NLP)

## Overview
This project builds a binary text classifier that distinguishes spam messages from legitimate ("ham") SMS messages, using classic NLP preprocessing and TF-IDF feature extraction.

## Dataset
- **File:** `spam.csv` (SMS Spam Collection Dataset, UCI/Kaggle)
- Loaded with `latin-1` encoding; dropped extra unnamed junk columns and renamed `v1`/`v2` to `label`/`message`.
- Final dataset: 5,169 messages after cleaning (4,516 ham / 653 spam — **87.4% / 12.6%**, a notably imbalanced dataset).

## Approach
1. **Data Cleaning** — Removed junk columns, nulls, and duplicates.
2. **Class Distribution Check** — Confirmed class imbalance (important context for interpreting accuracy later).
3. **Text Preprocessing Pipeline** — Lowercased text, removed punctuation, removed stopwords, and applied stemming (Porter Stemmer).
4. **Feature Extraction** — Converted cleaned text into numeric features using TF-IDF (top 3,000 features).
5. **Train/Test Split** — 80/20 split, stratified by label to preserve class balance.
6. **Modeling** — Trained two classifiers:
   - Multinomial Naive Bayes (standard baseline for text classification)
   - Logistic Regression
7. **Evaluation** — Compared Accuracy, Precision, Recall, and F1-score, plus confusion matrices.
8. **Why Recall Matters** — Discussed why recall (catching actual spam) is especially important in this context, since missed spam is a bigger practical problem than an occasional false positive.
9. **Bonus: Word Clouds** — Visualized the most frequent words in spam vs. ham messages.

## Results

| Model | Accuracy | Precision | Recall | F1-score |
|---|---|---|---|---|
| Multinomial Naive Bayes | **97.3%** | 99.0% | 79.4% | **88.1%** |
| Logistic Regression | 95.6% | **100.0%** | 64.9% | 78.7% |

**Multinomial Naive Bayes performed better overall**, achieving a stronger F1-score by catching significantly more spam messages (79.4% recall vs. 64.9%) while still keeping precision very high (99%). Logistic Regression had perfect precision (no false alarms) but missed over a third of actual spam messages — a worse trade-off for a spam filter, where failing to catch spam is generally costlier than an occasional false positive.

## Tech Stack
- Python
- pandas, NumPy
- Matplotlib, Seaborn, WordCloud
- NLTK (stopwords, stemming)
- scikit-learn (TF-IDF, Multinomial Naive Bayes, Logistic Regression)

## How to Run
1. Place `spam.csv` in the same directory as the notebook.
2. Install dependencies: `pip install pandas numpy matplotlib seaborn scikit-learn nltk wordcloud`
3. Open and run `spam_detection.ipynb` cell by cell in Jupyter Notebook (it will download NLTK stopwords automatically on first run).

## Project Structure
```
DataScience-Task4-SpamDetection/
├── spam_detection.ipynb
├── spam.csv
├── README.md
└── screenshots/
```
