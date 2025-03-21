# **Detecting Anomalies in Blockchain Transactions Using Machine Learning Classifiers and Explainability Analysis**

---

## **Abstract**
- The rise of **blockchain-based digital payments** has increased susceptibility to **malicious attacks**.
- **Anomaly detection** in blockchain transactions is critical but challenging due to **data imbalance**.
- **Key Contributions:**
  1. **Introduced XGBCLUS**, a novel under-sampling algorithm for balancing anomalous/non-anomalous data.
  2. Compared **XGBCLUS** with traditional under-sampling & over-sampling methods.
  3. Evaluated **single machine learning (ML) classifiers vs. ensemble models (stacking & voting).**
  4. **SHAP (Shapley Additive Explanations) applied for model explainability.**
  5. Developed **decision tree-based rules** for interpreting Bitcoin transaction anomalies.

---

## **1. Introduction**
- **Blockchain stores digital transactions** securely in a **decentralized ledger**.
- Used in **cryptocurrencies (Bitcoin, Ethereum, etc.)**, healthcare, IoT, and transportation.
- **Major vulnerabilities:** security breaches, privacy concerns, energy consumption, regulatory issues.
- **Problem:**
  - Bitcoin transactions are **prone to fraud, money laundering, & attacks** (e.g., temporal, spatial, and partitioning attacks).
  - **Existing ML-based detection models lack transparency (black-box issue).**
  - **Imbalanced dataset issue**: fraudulent transactions are **rare**, making detection difficult.

---

## **2. Proposed Solution**
- **Developed XGBCLUS**, an under-sampling algorithm to improve model learning for anomalies.
- Used **tree-based ML classifiers** for anomaly detection:
  - **Decision Tree (DT), Random Forest (RF), Gradient Boosting (GBoost), Adaptive Boosting (AdaBoost).**
- **Implemented ensemble classifiers (stacking & voting) to enhance accuracy.**
- **Applied SHAP for feature interpretability** and decision tree-based anomaly rules.

---

## **3. Dataset & Preprocessing**
- **Bitcoin transaction dataset from IEEE Data Portal (2011–2013).**
- **30,248,134 transactions** (only **108 labeled as anomalous** → highly imbalanced!).
- **Feature selection using T-tests & correlation matrix analysis.**
- **Key Features Identified:**
  - **Total BTC** (strongest anomaly indicator!)
  - **Mean incoming & outgoing BTC**
  - **Indegree & outdegree (number of inputs & outputs per transaction).**
- **Data balancing applied to avoid bias towards normal transactions.**

---

## **4. Data Balancing Techniques**
### **Under-Sampling Methods** (reduce normal transactions to balance with anomalies)
✅ **XGBCLUS (Proposed Algorithm)** → *Best performer!*
✅ Random Under Sampling (RUS) → Risk of losing useful data.
✅ NearMiss-1 → High True Positive Rate (TPR) but high False Positive Rate (FPR).

### **Over-Sampling Methods** (generate synthetic anomalies)
✅ **ADASYN (Best among oversampling)** → *Balances class distribution dynamically.*
✅ **SMOTE** → Generates synthetic data but may introduce bias.
✅ **SMOTEENN & SMOTETOMEK** → Hybrid techniques combining synthetic data & noise filtering.

### **Comparison Results:**
| Method | **TPR** | **FPR** |
|------------|--------|--------|
| **XGBCLUS (Proposed)** | **0.91** | **0.14** |
| RUS | 0.64 | 0.26 |
| NearMiss-1 | 0.99 | 0.99 |
| **ADASYN (Best Over-Sampling)** | **0.55** | **0.06** |

🔹 **XGBCLUS achieves the best trade-off between TPR and FPR.**

---

## **5. Machine Learning Models & Performance**
### **Single ML Models:**
- **Decision Tree (DT), Random Forest (RF), Gradient Boosting (GBoost), Adaptive Boosting (AdaBoost).**
- **Struggle with imbalanced data → Biased towards normal transactions.**

### **Ensemble Models:**
- **Stacking Ensemble**: Combines multiple classifiers with a meta-classifier.
- **Voting Classifier (Hard & Soft Voting)**: Aggregates predictions from multiple models.

### **Best Results:**
| Model | **Accuracy** | **TPR** | **FPR** |
|------------|------------|------------|------------|
| **Stacked Ensemble** | 0.96 | 0.91 | 0.14 |
| **Hard Voting Ensemble** | **0.97** | **0.91** | **0.03** |
| Soft Voting Ensemble | 0.96 | 0.91 | 0.17 |

🔹 **Hard Voting Ensemble achieves the highest accuracy & lowest FPR! 🎯**

---

## **6. Explainability via SHAP Analysis**
- **SHAP (Shapley Additive Explanations) identifies top contributing features.**
- **Feature Importance Ranking:**
  1. **Total BTC (most influential feature).**
  2. **Mean Incoming BTC.**
  3. **Mean Outgoing BTC.**
- **SHAP-based visualizations confirm that transactions with higher total BTC tend to be anomalous.**

---

## **7. Anomaly Rules (Decision Tree Interpretation)**
- **Generated human-readable rules for anomaly detection.**
- **Example Rule:**
  - *If total BTC > 616.683 and mean incoming BTC ≤ 1047.517 → Transaction is anomalous.* ✅
- **Confidence Score:** 100% (Highly accurate!).

---

## **8. Comparison with Existing Studies**
| Study | Accuracy | FPR | Explainability? |
|------------|------------|------------|------------|
| **Shafiq (2022)** | 0.94 | 0.05 | ❌ No |
| **Sayadi (2021)** | 0.90 | 0.09 | ❌ No |
| **This Study (2024)** | **0.97** | **0.03** | ✅ Yes |

🔹 **Proposed model achieves the highest accuracy & lowest false positives while being explainable! 🚀**

---

## **9. Conclusion & Future Work**
- **XGBCLUS + Ensemble Learning = Best Blockchain Anomaly Detection Approach.**
- **SHAP-based explanations enhance transparency.**
- **Anomaly detection rules improve interpretability.**
- **Future work:**
  - Apply model to **real-time blockchain anomaly detection**.
  - Extend approach to **Ethereum, credit card fraud, & money laundering detection.**
  - Explore **deep learning & generative AI-based anomaly detection.**

---

## **🔹 Final Takeaway**
✅ **This study presents a robust, explainable, and highly accurate ML-based approach for detecting blockchain transaction anomalies.**

✅ **XGBCLUS + Ensemble Learning = State-of-the-art blockchain security solution.** 

✅ **SHAP explanations & decision rules make the model trustworthy & interpretable.**

✅ **Significant improvement over previous studies in accuracy & false positive reduction.**

---


