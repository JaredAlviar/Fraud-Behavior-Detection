# Financial Behavioral Simulation & Fraud Detection

### Project Overview
This project involves the creation of a **synthetic dataset engine** designed to simulate 100,000 credit card transactions. By engineering custom behavioral logic, I have created a "ground truth" environment to test and train fraud detection algorithms.

### Key Features
* **Probabilistic Modeling:** Used NumPy to generate a 5% fraud distribution across a 10,000-user base.
* **Behavioral 'Signatures':** Programmed specific fraudulent patterns, including:
    * Anomalous spending peaks (10x normal transaction volume).
    * Off-hour activity windows (1 AM – 6 AM) to simulate compromised account usage.
    * Category-specific pivots into high-resale sectors (Electronics & Travel).
* **Tech Stack:** Python, Pandas, NumPy.

### Current Status: Phase 2 (Active Development)
Currently implementing a **Random Forest Classifier** to perform binary classification on transaction data, focusing on optimizing precision-recall metrics to accurately distinguish between fraudulent and legitimate activity.
