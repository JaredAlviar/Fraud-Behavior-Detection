# Fraud Behavior Detection/Simulation: Credit Card Fraud & Anomaly Audit
**Author:** Jared Alviar  

## Project Goal
The objective of this project is to simulate an enterprise financial transaction environment and evaluate an automated fraud detection pipeline under realistic class imbalance. Using NumPy and Pandas, we synthesize 100,000 credit card transactions mapped across 10,000 unique users, inject behavioral anomaly signatures reflecting real-world fraud schemes, evaluate a baseline classifier on a held-out test split, and serve an interactive natural-language auditing agent via Streamlit.

## Key Features

- **Scalable Data Simulation:** Generates 100,000 raw transaction records cross-referenced with 10,000 user profiles, maintaining an authentic 5% fraud class distribution (95% legitimate, 5% fraudulent).
- **Behavioral Pattern Injection:** Simulates three distinct fraudulent mechanisms:
  - **Pattern A (Financial Profile Mismatch):** Low credit scores (300–500) paired with elevated annual incomes ($120k–$500k), reflecting compromised high-value accounts.
  - **Pattern B (Temporal Off-Hours Exploitation):** Skewed transaction activity concentrated between 12:00 AM and 5:00 AM to bypass immediate cardholder push notifications.
  - **Pattern C (Merchant Category Bias):** High-liquidity merchant targeting focused exclusively in Electronics and Travel.
- **Empirical Held-Out Validation:** Evaluates an 80/20 stratified Random Forest baseline (`n_estimators=100`, `max_depth=10`) on 20,000 unseen test records.
- **Conversational Audit Interface:** Streamlit dashboard utilizing LLM tool execution to translate natural-language compliance inquiries into deterministic Pandas filter operations.

## Held-Out Model Evaluation Results

To evaluate detection performance under severe class imbalance, the 100,000-transaction dataset was split into an 80/20 stratified train/test split. The classifier was trained on 80,000 samples and evaluated against 20,000 unseen test records.

### Benchmark Metrics (20,000 Held-Out Samples)
| Metric | Score | Description |
| :--- | :--- | :--- |
| **Precision** | **1.0000** | Zero false positives across 19,079 legitimate cardholder transactions. |
| **Recall** | **0.7980** | Caught 735 of 921 fraudulent transactions (~80% coverage). |
| **F1-Score** | **0.8877** | Harmonic balance between coverage and precision under class imbalance. |
| **ROC-AUC** | **0.9986** | Near-optimal class separation across probability thresholds. |
