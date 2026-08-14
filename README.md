# Predicting U.S. Treasury Yield Curve Reactions to FOMC Announcements
## Problem Statement
Federal Open Market Committee (FOMC) announcments can generate quick and heterogeneous movements across the U.S. Traeasury yield curve. Fixed-income traders must quickly detemrine whether a policy decision is oikely to produce rising or falling yields and a steepening or falttening of the curve. This matters beacuse for a multi asset portfolio, the changes in the curve could directly impact to the company's profit and loss. The same policy-rate decision may vary depending on prior expectations, pevailing macroeconomic conditions,m and the language used in the FOMC statement. 

This project aims to develop a machine-learning model that estimates the probabilities of different post-announcemnt yield-curve reactions using information avaliable before and immediately after a FOMC announcement. Potential inputs include the policy-rate decision, measures of the monetary policy surprise, recent inflation and labor-market data, pre-announcement Treasury yields, the shape and volatility of the curve, and features extracted from the FOMC statement. 
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
<Descriptive / Predictive / Causal; metric; artifact to deliver>
## Assumptions & Constraints
<Bullets: data availability, capacity, latency, compliance, etc.>
## Known Unknowns / Risks
<Bullets: what’s uncertain; how you’ll test or monitor>
## Lifecycle Mapping
Goal → Stage → Deliverable
- <Goal A> → Problem Framing & Scoping (Stage 01) → <Deliverable X>
- ...
## Repo Plan
data/, src/, notebooks/, docs/ ; cadence for updates