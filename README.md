# Predicting U.S. Treasury Yield Curve Reactions to FOMC Announcements
## Problem Statement
Federal Open Market Committee (FOMC) announcements can generate quick and heterogeneous movements across the U.S. Treasury yield curve. Fixed-income traders must quickly determine whether a policy decision is likely to produce rising or falling yields and a steepening or flattening of the curve. This matters because for a multi asset portfolio, the changes in the curve could directly impact to the company's profit and loss. The same policy-rate decision may vary depending on prior expectations, prevailing macroeconomic conditions, and the language used in the FOMC statement. 

This project aims to develop a machine-learning model that estimates the probabilities of different post-announcement yield-curve reactions using information available before and immediately after a FOMC announcement. Potential inputs include the policy-rate decision, measures of the monetary policy surprise, recent inflation and labor-market data, pre-announcement Treasury yields, the shape and volatility of the curve, and features extracted from the FOMC statement. 
## Stakeholder & User
The primary stakeholder is a fixed-income trading desk or portfolio manager responsible for U.S. interest-rate exposure. The principal end user is a rates trader who must interpret an FOMC announcement and decide whether to adjust duration, curve, or hedging positions.
The model would support, rather than automatically execute, trading and risk-management decisions.

## Useful Answer & Decision

This is primarily a predictive problem. The model will estimate the probability of each of the following post-announcement curve reactions:

Bull steepening: yields decline, with short-term yields declining more than long-term yields.
Bull flattening: yields decline, with long-term yields declining more than short-term yields.
Bear steepening: yields rise, with long-term yields rising more than short-term yields.
Bear flattening: yields rise, with short-term yields rising more than long-term yields.
Limited reaction: changes in yields and curve slope remain below a predefined threshold.

The model's output will be a probability distribution rather than only a single predicted class. For example:

Bear flattening: 45%
Bear steepening: 20%
Limited reaction: 18%
Bull flattening: 10%
Bull steepening: 7%

The end user could use these probabilities to support decisions such as:

Increasing or reducing portfolio duration.
Entering, maintaining, or closing a steepener or flattener position.
Adjusting hedges at specific points of the yield curve.
Reducing exposure when the model indicates a high probability of a large or uncertain reaction.

## Assumptions & Constraints
- The project will first only focus on determining the prediction of the outcomes of the FOCM policy without the language. Then it will incorporate the language and the last incorporations would be adding other predictive measures to strengthen the prediction, such as macroeconomic factors or other annoucements like employment. 
- It will only focus on 2y and 10y yields and their spread of the treasury curve
- Historical U.S. Treasury yield data are available for the required maturities, initially the 2-year and 10-year tenors. Then It can change to other tenors
- A consistent post-announcement measurement window can be constructed from the available market data.
- No proprietary employer data or code will be used.
## Known Unknowns / Risks
- *Small sample size:* There are only a limited number of FOMC announcements each year. The initial model will therefore use regularization, simple baselines, time-aware validation, and limited model complexity.
- *Reaction-window definition:* Daily data may include market movements that occurred before the announcement, while intraday data may be difficult to obtain. Different event windows will be tested based on data availability.
- *Look-ahead bias:* Macroeconomic data are frequently revised. When possible, the project will use release-date values or historical vintages rather than revised values.
Economic usefulness: Statistical classification accuracy may not translate directly into profitable or risk-reducing decisions after transaction costs.
- *Policy-surprise measurement:* A reliable historical measure of market expectations may not be freely available for the complete sample.
## Lifecycle Mapping
Goal → Stage → Deliverable
- Define the decision-relevant prediction problem → Problem Framing & Scoping (Stage 01) → Project scoping statement and stakeholder memo.
## Repo Plan

```text
fomc-treasury-curve-reactions/
├── data/
│   ├── raw/
│   ├── processed/
│   └── README.md
├── docs/
│   └── stakeholder_memo.md
├── notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_exploratory_analysis.ipynb
│   └── 03_modeling.ipynb
├── src/
│   ├── data/
│   ├── features/
│   ├── models/
│   └── visualization/
├── .gitignore
├── LICENSE
└── README.md
```
