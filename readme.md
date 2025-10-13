# Shifting Stories – Shifting Returns

This project explores whether *narrative shifts in corporate disclosures* can be systematically transformed into trading signals.  

By analyzing quarterly reports, extracting structured narrative features, and applying various Moving Target Score (MTS) formulations, the study evaluates the predictive power of corporate storytelling in equity markets.

We test across **7 quarters** using a **long–short flipped strategy**, where the **top 10%** is taken as the **short portfolio** and the **bottom 10%** as the **long portfolio**.

---

## 📊 Key Results (Moving Targets)

| MT   | Mean Return | Stdev  | Sharpe | Hit Rate | Cum. Return |
|------------|------------:|-------:|-------:|---------:|-------------:|
| **KL**     | 0.0269      | 0.0586 | 0.46   | 0.75     | 0.22         |
| **Cosine** | 0.1158      | 0.2155 | 0.54   | 0.75     | 1.15         |
| **Euclid** | -0.1213     | 0.1862 | -0.65  | 0.00     | -0.71        |
| **Ham**    | -0.8650     | 2.1440 | -0.40  | 0.00     | -3.06        |
| **Costate**| -0.0726     | 0.0811 | -0.90  | 0.12     | -0.47        |
| **JS**     | -0.0052     | 0.0630 | -0.08  | 0.50     | -0.05        |

---



## 📂 Project Structure

⚠️ **Files where you'll need to insert Orbit/OpenAI API keys**:  
- `orbit_pdfs.ipynb`  
- `train_data.ipynb`  
- `openAI_embeddings.ipynb`  
- `categories_openAI_embeddings.ipynb`  

Notebooks:  
- **categories_openAI_embeddings.ipynb** – Building and testing category embeddings for financial and non-financial terms.  
- **feature_engineering.ipynb** – Feature extraction pipeline (sentiment, risk, forward-looking, subjective/objective, etc.).  
- **final_data_creation.ipynb** – Data preprocessing and final dataset generation.  
- **openAI_embeddings.ipynb** – Embedding generation using OpenAI models.  
- **orbit_pdfs.ipynb** – Scripts for handling and parsing Orbit dataset PDFs.  
- **train_data.ipynb** – Initial training data preparation.  
- **analysis.ipynb** – Strategy evaluations.  

---

## 🚀 Methodology

1. **Data Collection**: Quarterly reports (Orbit dataset) were processed into sentence/block structures.  
2. **Feature Engineering**: Extracted multi-dimensional features including:
   - Financial & Business categories (via OpenAI embeddings)  
   - Risk (MNLI classification)  
   - Analyst interaction  
   - Subjective vs. Objective phrasing  
   - Forward-looking vs. Historical statements  
   - Sentiment (FinBERT)  
3. **Signal Construction**: Moving Target Scores (MTS) quantify quarter-to-quarter narrative shifts.  
4. **Strategy Evaluation**:  
   - Long-short portfolios formed using top/bottom deciles of MTS signals.  
   - Multiple variants tested (variance-weighted, frequency-weighted, EWMA, Kalman, etc.).  
   - Factor regressions run to benchmark alpha and exposures.  

---

## 📈 Key Insights

- Narrative shifts are frequent: ~20 features change per firm per quarter.  
- Extreme changes (Bang-Bang Max Delta) align best with return direction.  
- Non-financial shifts often foreshadow financial deterioration.  
- EWMA and Kalman MTS variants delivered strong raw returns but were highly volatile and factor-loaded.  
- Variance-weighted MTS produced smoother returns but lacked tradable alpha.  
- Combined strategies stabilized volatility but provided limited standalone alpha.  

---

## 📁 Full Report & Conference Presentation

A detailed write-up covering methodology, results, and conclusions is available here:
🔗 [**Full Report – Shifting Stories – Shifting Returns (GitHub)**](https://github.com/komalniraula/Shifting-Stories---Shifting-Returns/blob/main/Shifting%20Returns%20%28Alphathon%20Q3%29.pdf)

The presentation slides with key insights and findings can be found here:
🎥 [**Presentation – Shifting Stories – Shifting Returns (PPT)**](https://github.com/komalniraula/Shifting-Stories---Shifting-Returns/blob/main/shifting_returns_ppt.pdf)

---