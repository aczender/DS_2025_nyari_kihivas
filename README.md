# IMDb Watchlist Sentiment Analysis

## Overview
This project was developed during my role as a Junior Data Analyst.  
The goal was to **scrape IMDb watchlist data** and perform **sentiment analysis** on movie plots and summaries using both Hugging Face models and ChatGPT.  
The results were then compared to evaluate differences in sentiment classification methods.

## Objectives
- Collect every item from my personal IMDb watchlist.
- Build a structured dataset including:
  - Title  
  - Rating  
  - Release Year  
  - Plot  
  - Summary  
- Handle missing or incomplete entries.
- Apply sentiment analysis on text fields using:
  - Hugging Face `DistilBERT` sentiment model.  
  - ChatGPT (prompt-based classification).  
- Compare results across methods.

## Data
- Source: [IMDb personal watchlist](https://www.imdb.com/user/ur40669107/watchlist/?ref_=tt_nv_urwls_all)  
- Initial dataset: **2723 items**  
- Final dataset used: **2491 items** (after cleaning)  
  - Removed 221 items (missing year)  
  - Removed 5 items (missing plot, 2 already excluded earlier)  
  - Removed 12 items (other missing data)  

## Tools & Libraries
- **Environment**: Google Colab → migrated to Jupyter Notebook
- **Libraries**:  
  - `pandas`  
  - `seaborn`  
  - `selenium`  
  - `pytorch`  
  - Hugging Face `transformers` (DistilBERT sentiment classifier)  
- **Other tools**:  
  - `ChatGPT` for alternative sentiment analysis (via CSV upload and prompt processing)

## Results

### Plot-based Sentiment (Hugging Face DistilBERT)
- Strongly Negative → 1,056 movies  
- Negative → 30 movies  
- Positive → 39 movies  
- Strongly Positive → 1,366 movies  

### Summary-based Sentiment (Hugging Face DistilBERT)
- Strongly Negative → 281 movies  
- Negative → 126 movies  
- Neutral → 308 movies  
- Positive → 357 movies  
- Strongly Positive → 1,419 movies  

### ChatGPT Sentiment (Plot-based)
- Strongly Negative → 448 movies  
- Negative → 861 movies  
- Neutral → 461 movies  
- Positive → 721 movies  

### Distribution Comparison
- **Hugging Face**: 43.59% Negative, 56.41% Positive  
- **ChatGPT**: 52.54% Negative, 28.94% Positive, remainder Neutral  

## Key Challenges
- IMDb frequently changes backend code → scraper must be updated regularly.  
- Ambiguity in AI sentiment classification results.  
- Google Colab usage limits required migration to Jupyter Notebook.  

## Lessons Learned & Next Steps
- Improve deduplication during web scraping.  
- Handle missing year values more intelligently (series start/end dates).  
- Explore alternative sentiment analysis methods (e.g., Claude).  
- Run repeated experiments to validate consistency.  
- Optimize scraping logic or switch to the **IMDb API** for efficiency.  

## Author
Developed as a learning project during my time as a **Junior Data Analyst**.  
