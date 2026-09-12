# Advanced Multi-Target Classification of Cybersecurity Threats
## Leakage-Safe XGBoost + CatBoost Ensemble with ML-SMOTE and SHAP — CIC-DDoS2019

This repository contains the experimental pipeline and revised code for the research paper/project **"Advanced Multi-Target Classification of Cybersecurity Threats"**, rebuilt on the large, public **CIC-DDoS2019** benchmark (cleaned parquet release) in response to peer-review feedback.

---

## Author
* **Sunawar Khan**  
* Repository: [Advanced-Multi-Target-Classification-of-Cybersecurity-Threats](https://github.com/SunawarKhan/Advanced-Multi-Target-Classification-of-Cybersecurity-Threats.git)

---

## Key Highlights & Reviewer-Driven Improvements
* **Dataset Scale:** Moved from a small data breach set (with constant labels and vacuous metrics) to the large **CIC-DDoS2019** benchmark (**125,170** labeled flows; stratified 40,000-flow working sample).
* **Multi-Target Hierarchy:** Formulated four non-constant, security-meaningful hierarchical targets (`IsAttack`, `IsReflection`, `IsPortmap`, `IsNetBIOS`) spanning the difficulty spectrum based on the official DDoS taxonomy (Sharafaldin et al., 2019).
* **Advanced Resampling:** Implemented **ML-SMOTE** (Charte et al., 2015) for multi-label minority class oversampling, with empirical comparisons against ROS, SMOTE, ADASYN, and SMOTEENN.
* **Ensemble Optimization:** Documented soft-voting weight grid search (inner 3-fold CV) combining XGBoost and CatBoost.
* **Multi-Label Strategies:** Rigorous comparison between **Binary Relevance**, **Classifier Chains**, and **Label Powerset**.
* **Statistical Evaluation:** Includes PR-AUC, F1-score, balanced accuracy, full confusion matrices, and paired **Wilcoxon signed-rank tests** with **Holm–Bonferroni** correction.
* **Explainability:** Global and local **SHAP** explanations featuring real, interpretable flow feature names.
* **Profiling:** Throughput, memory, and runtime profiling suitable for SIEM deployment claims.

---

## Environment & Requirements
* **Python:** 3.12.3
* **Core Libraries:** NumPy, pandas, scikit-learn, XGBoost, CatBoost, SHAP, imbalanced-learn, SciPy, matplotlib

To install necessary dependencies, run:
```bash
pip install numpy pandas scikit-learn xgboost catboost shap imbalanced-learn scipy matplotlib
```

---

## Repository Structure
The primary experimental notebook is structured into the following sequential sections:
1. **Environment and Reproducibility**
2. **CIC-DDoS2019 Loading & Multi-Target Label Derivation**
3. **Leakage-Safe Preprocessing & ML-SMOTE**
4. **Ensemble Weight Selection (Inner 3-Fold CV)**
5. **Outer 5-Fold Cross-Validation (Ensemble vs. Baselines)**
6. **Multi-Label Strategy & Resampling Comparisons**
7. **Statistical Significance Testing (Wilcoxon + Holm-Bonferroni)**
8. **Explainability with Real Feature Names (SHAP)**

---

## Citation
If you use this repository, code, or experimental framework in your research, please cite it as follows:

```bibtex
@software{Khan_Advanced_Multi_Target_Classification_2026,
  author = {Sunawar Khan},
  title = {{Advanced Multi-Target Classification of Cybersecurity Threats}},
  year = {2026},
  url = {https://github.com/SunawarKhan/Advanced-Multi-Target-Classification-of-Cybersecurity-Threats.git}
}
```

---

## References
* Sharafaldin, I., Lashkari, A. H., & Ghorbani, A. A. (2019). Toward Generating a New Intrusion Detection Dataset and DDoS Attack Characterization. *ICISSP*.
* Charte, F., Rivera, A. J., del Jesus, M. J., & Herrera, F. (2015). ML-SMOTE: Approaching imbalanced multilabel classification through sample interpolation. *Knowledge-Based Systems*, 89, 385-397.
