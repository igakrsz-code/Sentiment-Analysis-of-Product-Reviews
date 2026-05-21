# Amazon Product Reviews — Sentiment Analysis

A data analysis project that cleans Amazon product review data, explores sentiment patterns, and trains a Naive Bayes model to classify reviews as positive or negative.

## Dataset

Amazon India product reviews downloaded from the course repository.  
The raw file had one row per product with multiple reviews packed into each cell — these were expanded to **21,357 individual reviews** across 9 product categories.

## Project Structure

```
├── sentiment_analysis.ipynb   # main notebook
├── amazon.csv                 # raw dataset
├── amazon_reviews.xlsx        # cleaned data + analysis exported to Excel
└── README.md
```

## What the notebook does

1. **Load and clean the data** — expands packed review rows, parses ratings, drops empty rows
2. **Add sentiment labels** — rating >= 4.2 → Positive, < 3.9 → Negative, in between → Neutral
3. **Export to Excel** — four sheets:
   - *Reviews* — cleaned data with `LEN`, `FIND`, and `SUBSTITUTE` formulas in columns G–I
   - *Word Frequency* — count of positive vs negative signal words across all reviews
   - *Sentiment by Category* — pivot-style summary of sentiment per product category
   - *ML Predictions* — model predictions compared to actual ratings
4. **Exploratory analysis** — charts for rating distribution, sentiment breakdown, word frequencies, sentiment by category
5. **Machine Learning** — Naive Bayes classifier trained to predict positive vs negative reviews

## Results

| Metric | Value |
|--------|-------|
| Total reviews | 21,357 |
| Positive reviews | 10,249 |
| Negative reviews | 2,907 |
| Neutral reviews | 8,201 |
| Model accuracy | 64.7% |

**Top positive words:** good, quality, nice, best, easy  
**Top negative words:** issue, problem, bad, cheap, poor

## How to run

1. Make sure `amazon.csv` is in the same folder as the notebook
2. Install dependencies: `pip install pandas numpy matplotlib seaborn scikit-learn openpyxl`
3. Open `sentiment_analysis.ipynb` in Jupyter and run all cells

## Tools used

- Python, pandas, numpy
- matplotlib, seaborn
- scikit-learn (Naive Bayes, CountVectorizer)
- openpyxl (Excel export)
