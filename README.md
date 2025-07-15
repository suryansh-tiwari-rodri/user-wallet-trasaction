# user-wallet-trasaction
 a robust machine learning model that assigns a credit score between 0 and 1000 to each wallet, based solely on historical transaction behavior. 
# Aave V2 DeFi Wallet Credit Scoring

This project assigns a **credit score between 0 and 1000** to DeFi wallets based on their transaction history on the Aave V2 protocol. The scoring reflects a wallet's reliability, risk behavior, and usage patterns.

---

* Objective

To develop a machine learning-based scoring engine using raw transaction data (`deposit`, `borrow`, `repay`, `redeemunderlying`, `liquidationcall`) and assign a 0–1000 score to each wallet.

---

 * Architecture & Flow

1. Raw Data Input:
   - JSON file containing historical Aave V2 transactions.

2. Feature Engineering:
   - Total transaction count
   - Frequency of each action type
   - Total and average transaction amount
   - Time gaps between transactions
   - Repay-to-borrow ratio
   - Liquidation frequency

3. Unsupervised Clustering:
   - Normalize all features using `MinMaxScaler`
   - Cluster behavior patterns using KMeans (5 clusters)

4. Score Assignment:
   - Assign scores (0–1000) based on cluster:
     - Risky → 200
     - Reliable → 1000

5. Output:
   - `wallet_scores.csv` with `wallet` and `credit_score` columns.
---
* Why KMeans?

- No labeled ground truth available
- Behavioral clustering is ideal for grouping usage types (bots, whales, stable users)
- Flexible to adapt and expand with labeled fraud data

---

* Output Files

- `wallet_scores.csv`: Final credit scores
- `analysis.md`: Score behavior insights & plots

---

* Requirements

- Python 3.x
- pandas, numpy, scikit-learn, matplotlib, tqdm

---

* Usage

Upload your JSON file and run the notebook. Scores are generated in one step and exported as a CSV file for further analysis or app integration.
