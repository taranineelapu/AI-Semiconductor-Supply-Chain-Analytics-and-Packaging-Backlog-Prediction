# AI Semiconductor Chips Supply Chain Analytics & Packaging Backlog Prediction

**Project objective:** Identify semiconductor chips production bottlenecks, assess operational risk, predict packaging delays, and help operations managers prioritize delays to meet rising demand and optimize revenue.

**Interactive Tableau dashboards:** [Supply chain operations overview](https://public.tableau.com/views/AISemiconductorSupplyChain-OperationsOverview/Dashboard1-AISemiconductorSupplyChain-OperationsOverview?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link) · [Packaging backlog prediction](https://public.tableau.com/views/AISemiconductorPackagingBacklogPredictionOperationalPrioritization/Dashboard2-PredictiveBacklogAnalysis?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

> **Note**: This project utlizes synthetic data for demonstration purposes.

---

## Business Context

The rapid expansion of AI infrastructure has increased the demand for manufacturing semiconductor chips. As production volumes increase, packaging backlogs is a key contributer for supply chain bottlenecks affecting delivery timelines.

This project analyzes semiconductor chips supply chain dataset using **exploratory data analysis, regression models, and data visualization** to identify factors contributing to packaging backlogs and develop a machine learning model to predict packaging backlog duration.

- Analyze backlog patterns across manufacturing facilities, geographic regions, and packaging technologies to identify operational constraints.
- Investigate how manufacturing capacity, facility utilization, process technology, and other operational factors influence packaging delays.
- Build, evaluate and compare regression models to predict packaging backlog duration.
- Develop a facility-level priority scoring methodology to identify manufacturing sites requiring operational attention.
- Export model predictions and operational insights to Tableau for monitoring bottlenecks, assessing facility performance, and supporting capacity planning.

## Executive Summary

- This project analyzes semiconductor chips supply chain operations to identify production bottlenecks, assess supply chain risks, and predict packaging delays. We are using Python, regression models, and Tableau, the analysis combines manufacturing performance metrics with predictive analytics to understand where operational constraints occur.

- The project includes two interactive Tableau dashboards. The first examines wafer capacity, utilization, production yield, packaging backlogs, and supply chain vulnerabilities. The second uses regression model predictions to estimate packaging delays and identify facilities that may require operational attention.

- The analysis helps operations managers monitor supply chain performance, anticipate potential packaging delays, and prioritize facilities for further investigation. These insights support data-driven capacity planning, resource allocation, and operational decision-making.

## Methodology

**Step 1: Data Preprocessing:** 

  Cleaned and validated semiconductor chips supply chain data by checking missing values, duplicates, and inconsistencies to ensure data quality for analysis and predictive modeling.

**Step 2: Exploratory Data Analysis (EDA):**

   Analyzed wafer capacity, facility utilization, packaging backlogs, and manufacturing characteristics to identify production bottlenecks and potential supply chain risks.

**Step 3:Predictive Modeling:**

   Built and compared regression models, including Bayesian Ridge, LightGBM, and CatBoost, to predict packaging backlog duration. Evaluated model performance using MAE, RMSE, and R².

**Step 4: Operational Prioritization:**

   Developed a facility-level Backlog Attention Score combining predicted packaging delays (70%) and capacity utilization (30%) to identify facilities requiring closer operational attention.

**Step 5: Data Visualization:**

   Created two interactive Tableau dashboards to visualize manufacturing performance, supply chain vulnerabilities, predicted packaging delays, and facility-level operational priorities.

## Key Findings

## Key Findings

### 1. Advanced Packaging Technologies Experience the Longest Delays

Analysis of **10,000 semiconductor facility records** revealed significant differences in packaging backlog across technologies.

| Packaging Technology | Average Backlog (Weeks) |
|---|---:|
| Foveros-3D | 28.19 |
| CoWoS-S | 28.00 |
| CoWoS-L | 27.97 |
| InFO-PoP | 11.42 |
| Standard FlipChip | 6.10 |

Advanced packaging technologies such as **CoWoS and Foveros-3D experience approximately 4–5 times longer backlogs** than standard FlipChip packaging, highlighting potential capacity constraints in advanced packaging operations.

### 2. Advanced Process Nodes Face Higher Packaging Backlogs

Manufacturing facilities using **2nm–5nm process nodes** experienced average packaging backlogs of approximately **24 weeks**, compared with 10–13 weeks for 7nm–28nm nodes.

This suggests that facilities supporting advanced semiconductor manufacturing face greater packaging delays, making them important areas for operational monitoring and capacity planning.

### 3. Regression Models Explain Approximately 81% of Backlog Variation

Three regression models were evaluated using five-fold cross-validation to predict packaging backlog duration.

| Model | MAE (Weeks) | RMSE (Weeks) | R² |
|---|---:|---:|---:|
| Bayesian Ridge | 3.53 | 4.63 | 0.8079 |
| CatBoost | 3.55 | 4.65 | 0.8067 |
| LightGBM | 3.61 | 4.73 | 0.7999 |

**Bayesian Ridge achieved the best overall performance**, with a holdout test R² of **0.806** and an MAE of **3.51 weeks**.

The results demonstrate that regression models can estimate packaging backlog duration using manufacturing and product characteristics.

### 4. Packaging Technology Is the Strongest Predictor of Backlog

Permutation feature importance identified **advanced packaging type** as the most influential variable in the selected regression model, substantially exceeding the contribution of other manufacturing characteristics.

This indicates that the type of packaging technology is a major factor associated with backlog duration in the dataset.

### 5. Predictive Analytics Supports Facility-Level Operational Prioritization

The predictive model generated packaging backlog estimates for all **10,000 facilities**. A weighted Backlog Attention Score was developed using:

- **70% — Predicted Packaging Backlog**
- **30% — Capacity Utilization**

The scoring framework helps distinguish facilities with long predicted queues from those requiring greater operational attention based on both backlog and capacity utilization.

These insights support proactive bottleneck monitoring, facility prioritization, and data-driven capacity planning.

### End-to-End Analytical Workflow

```text
Semiconductor Supply Chain Dataset
             |
             v
      Data Preprocessing
             |
       +-----+------+
       |            |
       v            v
 Descriptive &   Regression Model
 Risk Analysis   Training/Evaluation
       |            |
       v            v
 Tableau          Predicted Backlog
 Dashboard 1      Analysis
                    |
                    v
                 Tableau
                 Dashboard 2
```

## Tools & Technical Skills

| Area | Tools and methods |
|---|---|
| Programming | Python, Pandas, NumPy, Seaborn, Matplotlib, scikit-learn |
| Visualization | Tableau, KPI design |
| Predictive analytics | Regression modeling, gradient-boosted decision trees |
| Model evaluation | MAE, RMSE, R² |
| Supply chain analytics | Capacity utilization, bottleneck analysis, facility prioritization, vulnerability assessment |
