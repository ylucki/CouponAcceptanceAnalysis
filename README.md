# Coupon Acceptance Analysis (Practical Application)

This repository answers a simple question: **Will a customer accept the coupon?**  
Using Python (pandas, NumPy) and visualizations (Matplotlib + Seaborn used in-notebook), we explore acceptance patterns across coupon types and driving context (time, weather, passengers, destination, etc.).

## Dataset
- Source: UCI Machine Learning Repository (survey via Amazon Mechanical Turk).  
- Responses: 
  - "Right away" or "Later, before the coupon expires" → **Y = 1 (accepted)**
  - "No, I do not want the coupon" → **Y = 0 (rejected)**

## Quick Findings
- Overall acceptance rate: 56.84%
- Highest acceptance: **Carry out & Take away** (73.5%); Lowest: **Bar** (41.0%).
- By time: top = **2PM** (66.2%); bottom = **7AM** (50.2%).
- By weather: top = **Sunny** (59.5%); bottom = **Rainy** (46.3%).
- By destination: top = **No Urgent Place** (63.4%); bottom = **Work** (50.2%).
- By expiration: top = **1d** (62.6%); bottom = **2h** (49.6%).

**Based on the the data analysis:**

- Coupon Type Matters: "Carry out & Take away" and "Restaurant(<20)" coupons have significantly higher acceptance rates compared to "Coffee House," "Restaurant(20-50)," and "Bar" coupons. Focus on promoting the higher-performing coupon types.
- Context is Key: Acceptance varies based on context variables:
- Time: Coupons offered at 2 PM and 10 AM have higher acceptance rates.
- Weather: Sunny weather correlates with higher acceptance.
- Passenger: People with "Friend(s)" or "Partner" are more likely to accept coupons.
- Destination: "No Urgent Place" destinations show higher acceptance.
- Expiration: Coupons with a 1-day expiration are more likely to be accepted than those with a 2-hour expiration.

**Actionable Ideas**
- Promote **high-acceptance coupon types** more prominently in-app and at relevant times (see charts in `images/`).
- **Target timing & context**: push coupons when acceptance is historically higher (e.g., top time-of-day or with certain passengers/destinations).
- **Shorter expiration** can depress acceptance; test **expiration windows** that match when users are most receptive.
- Tune Expiration Windows: Consider offering coupons with longer expiration times (like 1 day) to increase acceptance.
- Consider A/B Testing: Personalize offers by combining coupon type and context (e.g., offer "Carry out & Take away" coupons to people with friends during sunny weather at 2 PM when they are going to "No Urgent Place").
- Numerical Distributions: Examine the distributions of numerical features like temperature and distance to coupon to understand if they differ between accepted and rejected groups, which could inform further targeting strategies.


## Link to Notebook: [amazon_coupon_acceptance.ipynb](https://github.com/ylucki/CouponAcceptanceAnalysis/blob/main/notebooks/amazon_coupon_acceptance.ipynb)
## Project Structure
```
coupon-acceptance-project/
├─ data/
│  └─ coupons.csv
├─ images/
│  ├─ acceptance_by_coupon_type.png
│  ├─ acceptance_by_destination.png
│  ├─ acceptance_by_expiration.png
│  ├─ correlation_heatmap.png
│  ├─ age_distribution_by_acceptance.png
│  └─ ... (other exploratory and distribution plots)
├─ notebooks/
│  └─ amazon_coupon_acceptance.ipynb
├─ requirements.txt
├─ .gitignore
└─ README.md

```

## How to Run Locally
1. Clone or download this repo.
2. (Recommended) Create a virtual environment.
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook notebooks/Practical_Application_1.ipynb
   ```
5. Run all cells to reproduce the analysis and charts.

## License
MIT (feel free to reuse for learning).
