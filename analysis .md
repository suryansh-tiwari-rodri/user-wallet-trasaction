# Wallet Behavior Analysis

This analysis summarizes how wallets performed across credit score ranges and highlights behavioral trends observed from the Aave V2 transaction data.

---

## 📊 Score Distribution


<img width="681" height="377" alt="Screenshot 2025-07-15 140834" src="https://github.com/user-attachments/assets/1e612e23-871c-4202-aa0a-ba0f89e1344a" />

- **0–200**: High liquidation ratio, many borrows but few repayments
- **201–400**: Some usage diversity but still risk-prone (many borrows, few deposits)
- **401–600**: Balanced activity with moderate borrow/repay behavior
- **601–800**: Frequent depositors, rare liquidations, consistent usage
- **801–1000**: Highly stable users — regular deposits, prompt repayments, no risky behavior

---

## Behavioral Clustering Summary

| Cluster | Behavior Pattern | Risk Level | Assigned Score |
|---------|------------------|------------|----------------|
| 0       | Many borrows, few repayments, liquidations | High Risk     | 200            |
| 1       | Mixed activity with inconsistent repay | Medium Risk   | 400            |
| 2       | Moderate use of all features | Low Risk      | 600            |
| 3       | Heavy depositors, consistent activity | Reliable      | 800            |
| 4       | Ideal usage — high volume deposits and repayments | Very Reliable | 1000           |

---

##  Notes

- The model is unsupervised and rule-free, making it adaptable to new wallets and protocols.
- You can integrate labeled fraud/loan default data in the future to train supervised models.
