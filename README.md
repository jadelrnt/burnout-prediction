# Burnout Risk Prediction – Logit Model & Interactive App

> Predicting the probability of severe professional burnout using econometric modeling and a Streamlit interactive application.

**Master 1 Data Science – Université Paris-Est Créteil | May 2025**  
*Supervised by Sylvain Chareyron, Associate Professor in Economics*

---

## Overview

This project builds an end-to-end pipeline to **predict severe burnout risk** at the individual level, combining rigorous econometric methodology with a practical prevention tool.

The study is grounded in two major theoretical frameworks:
- **Karasek's model (1979)** — psychological demand, decision latitude, social support
- **Maslach Burnout Inventory (1981)** — emotional exhaustion, depersonalization, personal accomplishment

---

## Dataset & Sample

- **Sample size:** 11,213 working individuals
- **Source:** Survey data restricted to employed workers
- **Target variable:** Severe burnout (binary) — defined as a global MBI score ≥ 3rd quartile (Q3 = 7)

**Sample demographics:**

| Variable | Value |
|----------|-------|
| Women | 57.0% |
| Men | 43.0% |
| Mean age | 45.1 years |
| Median monthly income | €1,800 |

---

## Methodology

### MBI Score Construction
Reconstructed from **22 binary items** across three sub-scores:
- Emotional exhaustion (9 items)
- Depersonalization (5 items)
- Reduced personal accomplishment (8 items, reverse-coded)

**Global score statistics:**

| Statistic | Value |
|-----------|-------|
| Mean | 5.41 |
| Std dev | 2.68 |
| Median (Q2) | 5.0 |
| 3rd quartile (Q3) | 7.0 |
| Max | 20.0 |

### Econometric Model
Binary logistic regression with:
- Class imbalance correction via **sample weighting**
- Dummy encoding of categorical variables
- Verification of multicollinearity, linearity, stability and coefficient robustness
- **Heckman two-stage selection model** to test for selection bias → Mills inverse ratio non-significant → no structural selection bias detected

---

## Key Results

### Model Performance

| Metric | Value |
|--------|-------|
| AUC (ROC) | **0.81** |
| Accuracy | 81% |
| Recall | 63.5% |
| Precision | 42.3% |
| F1-score | 0.51 |
| AIC | 6,227.4 |

> Classification threshold set at **0.20** to maximize recall (prevention-oriented).

### Main Risk Factors (OR > 1)

| Factor | Odds Ratio |
|--------|-----------|
| Degrading tasks | ≈ 2.30 |
| Boredom at work | ≈ 2.10 |
| Mockery / hurtful remarks | ≈ 2.08 |
| Out-of-hours solicitations | ≈ 1.91 |
| Being male (controlling for all characteristics) | ≈ 2.16 |

> All significant at the 1% level.

### Main Protective Factors (OR < 1)

| Factor | Odds Ratio |
|--------|-----------|
| Work-life balance | ≈ 0.48 |
| Moral support | ≈ 0.51 |
| Perceived well-being | ≈ 0.66 |
| Income > €3,000/month | ≈ 0.71 |
| Ability to implement own ideas | ≈ 0.76 |

### Notable Finding on Gender
- Descriptively: 19.1% of women vs. 10.5% of men in severe burnout
- **But controlling for all characteristics: being male doubles the risk (OR ≈ 2.16, p < 0.001)**
- The logit model reveals hidden male vulnerabilities masked by raw statistics

---

## Interactive Application

🌐 **[burnout-app.streamlit.app](https://burnout-app.streamlit.app)**

A simple, accessible self-assessment tool built with **Streamlit**:
- Input: age, job type, working conditions, personal perceptions
- Output: estimated burnout probability, risk level, personalized prevention advice
- The logit model runs in the background in real time

---

## Stack

```
Python · pandas · statsmodels · scikit-learn · matplotlib · Streamlit
```

---

## Repository Structure

```
burnout-prediction/
│
├── README.md
├── burnout_analysis.ipynb     # Full analysis pipeline
├── rapport.pdf                # Full academic report (French)
└── data/
    └── README.md              # Data source description
```

---

## Limitations

- Correlational model — no causal inference
- Self-reported data → potential social desirability bias
- Reconstructed MBI score (close but not identical to the validated instrument)
- Burnout threshold (Q3) is empirical — justified but not universal

---

*This project combines statistical rigor with social utility — making burnout risk estimation accessible for prevention purposes.*
