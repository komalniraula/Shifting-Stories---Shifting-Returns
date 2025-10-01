# Shifting Stories – Shifting Returns

This project was developed for **Alphathon Q3** and explores whether *narrative shifts in corporate disclosures* can be systematically transformed into trading signals.  
By analyzing quarterly reports, extracting structured narrative features, and applying various Moving Target Score (MTS) formulations, the study evaluates the predictive power of corporate storytelling in equity markets.

---

## 📂 Project Structure

⚠️ **Files where you'll need to insert API keys**:  
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
   - Financial & Business categories (via embeddings)  
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

## 📑 Full Report

A detailed write-up, including requirements, methodology, results, and conclusions, is available here:  
👉 [Shifting Stories – Shifting Returns (GitHub)](https://github.com/komalniraula/Shifting-Stories---Shifting-Returns.git)

---
