# The Myth of the 45th Minute  
### Statistical Modeling & Bias-Controlled Analysis in R

---

## Project Overview

Football commentators widely claim that scoring just before halftime creates a decisive psychological advantage. However, teams that score late are often already leading.

This project aims to **separate the effect of goal timing from the effect of the scoreboard**, using statistical modeling and bias correction techniques.

This was a **group project**.  
I was responsible for leading the **R implementation**, including data transformation, feature engineering, model construction, and interpretation of results.

---

## Data Scope

- ~1.2 million matches processed  
- Top 5 European leagues  
- Seasons: 2016–2025  
- Event-level match data  

 **Note:**  
The dataset used in this analysis is private and cannot be shared.  
This repository includes the complete modeling pipeline, excluding raw data.

---

## Research Questions

1. Does scoring in the late first half increase winning probability beyond what the scoreline predicts?
2. Is this effect amplified when playing at home?

---

## Methodology

###  Bias Identification

Football match data is inherently home-centric. Modeling outcomes directly can inflate home advantage.

### Data Flipping Technique

To eliminate this bias:

- Each match record was duplicated and inverted  
- Home and away teams were swapped  
- Outcomes and goal indicators were mirrored  

This ensured symmetric modeling of team outcomes.

---

## Statistical Model

- **Model Type:** Multinomial Logistic Regression  
- **Package:** `nnet::multinom`  
- **Outcome Categories:** Win / Draw / Loss  

### Controlled Variables

- Halftime score (team vs opponent)  
- League strength  
- Home vs away status  
- Interaction term: Late Goal × Home  

---

## Key Results

- Scoring a late first-half goal nearly **doubles the odds of winning** (Odds Ratio ≈ 1.88)
- The timing effect remains statistically significant after controlling for the scoreline
- Home advantage does not significantly amplify wins
- However, when scored at home, a late goal reduces the odds of losing by approximately **35% (OR = 0.65)**

---

## Interpretation

- The psychological momentum of late goals is statistically supported
- Home advantage functions as a **protective mechanism**, preventing collapse rather than increasing dominance
- Teams playing away lack this additional defensive reinforcement

---

## Tools & Techniques

- R  
- tidyverse  
- Feature engineering  
- Bias correction (data flipping)  
- Multinomial regression  
- Odds ratio interpretation  
- Reproducible reporting with R Markdown  

---

## Skills Demonstrated

- Hypothesis-driven analysis  
- Statistical modeling & inference  
- Large-scale data transformation  
- Bias correction techniques  
- Team collaboration with technical ownership  
- Ethical handling of confidential data  

---

## Data Availability

The dataset is excluded due to confidentiality restrictions.  
All scripts reflect the complete analytical workflow used in the project.

---
