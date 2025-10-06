# Coupon Acceptance Analysis (Practical Application 1)

This repository answers a simple question: **Will a customer accept the coupon?**  
Using Python (pandas, NumPy) and visualizations (Matplotlib + Seaborn used in-notebook), we explore acceptance patterns across coupon types and driving context (time, weather, passengers, destination, etc.).

## Dataset
- Source: UCI Machine Learning Repository (survey via Amazon Mechanical Turk).  
- Responses: 
  - "Right away" or "Later, before the coupon expires" → **Y = 1 (accepted)**
  - "No, I do not want the coupon" → **Y = 0 (rejected)**

## Quick, Nontechnical Findings
- Overall acceptance rate: 56.84%
- Highest acceptance: **Carry out & Take away** (73.5%); Lowest: **Bar** (41.0%).
- By time: top = **2PM** (66.2%); bottom = **7AM** (50.2%).
- By weather: top = **Sunny** (59.5%); bottom = **Rainy** (46.3%).
- By destination: top = **No Urgent Place** (63.4%); bottom = **Work** (50.2%).
- By expiration: top = **1d** (62.6%); bottom = **2h** (49.6%).

**Actionable Ideas**
- Promote **high-acceptance coupon types** more prominently in-app and at relevant times (see charts in `images/`).
- **Target timing & context**: push coupons when acceptance is historically higher (e.g., top time-of-day or with certain passengers/destinations).
- **Shorter expiration** can depress acceptance; test **expiration windows** that match when users are most receptive.
- A/B test **personalized offers** combining coupon type + context (e.g., coffee house coupons on morning commutes).

## Project Structure
```
coupon-acceptance-project/
├─ data/
│  └─ coupons.csv
├─ images/
│  ├─ acceptance_by_coupon.png
│  ├─ acceptance_by_time.png
│  ├─ acceptance_by_weather.png
│  ├─ acceptance_by_passenger.png
│  ├─ acceptance_by_destination.png
│  └─ acceptance_by_expiration.png
├─ notebooks/
│  └─ Practical_Application_1.ipynb
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
