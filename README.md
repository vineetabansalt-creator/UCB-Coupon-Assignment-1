# Will a Customer Accept the Coupon?

**UC Berkeley ML & AI Program Practical Application 5.1**

## Overview

This project explores a dataset of driving coupon offers collected via Amazon Mechanical Turk. Drivers were presented with various scenarios and asked whether they would accept a coupon for a nearby restaurant, bar, or coffee house. The goal is to identify what distinguishes customers who accepted from those who did not.

**Notebook:** [coupon_analysis_assignment5.ipynb](./coupon_analysis_assignment5.ipynb)  
**Dataset:** [coupons.csv](./coupons.csv)

---

## Key Findings

**Overall acceptance rate: ~57%** â€” more than half of drivers accept a coupon when presented with one, but acceptance varies widely based on context.

### Bar Coupons (41% acceptance)
- Drivers who already visit bars frequently (3+ times/month) accepted at **77%** â€” nearly double the overall bar rate
- Having friends in the car boosted acceptance to **56%**; having kids dropped it to **21%**
- Younger drivers (21â€“26) were meaningfully more likely to say yes than drivers 36+
- The combination of being a regular bar visitor + no kids = acceptance rates above 60%

### Coffee House Coupons (50% acceptance)
- The best time window is **10AMâ€“2PM** â€” acceptance peaks during the natural coffee break hours
- Regular coffee drinkers (1â€“3x/month+) accepted at significantly higher rates than non-visitors
- **1-day expiration outperforms 2-hour** â€” more time flexibility means more acceptances
- Drivers with no urgent destination were the most receptive segment

---

## Recommendations

1. **Target existing behavior** â€” the strongest predictor across all coupon types is whether the driver already visits that venue. Coupons are most effective as reinforcement, not habit creation.
2. **Match timing to the coupon type** â€” coffee in the morning, bars in the evening.
3. **Avoid families for bar coupons** â€” presence of kids is a consistent negative signal.
4. **Use 1-day expiration** over 2-hour where possible â€” it consistently outperforms.

---

## Next Steps

- Build a classification model (Logistic Regression / Decision Tree) to predict acceptance
- Explore interaction effects between time, passenger type, and coupon type
- Investigate income and occupation as additional segmentation dimensions

