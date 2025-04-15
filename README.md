# Marketing_MMM_for_Campaign_ROI_Optimization

## 🎯 Project Goal

The aim here was simple: **Understand the return on investment (ROI)** from traditional media channels like **TV, radio, and newspaper**, then offer a smarter way to allocate ad budgets using regression modeling and simulation.
---
## 🧠 What I Did

- Cleaned and explored the advertising dataset (classic sales vs. spend example)
- Built a multiple linear regression model to link sales with ad spend
- Evaluated how much each channel contributed to performance
- Checked for multicollinearity and added lag/interaction features for deeper context
- Ran simulations to see what would happen if we shifted some spend from low-ROI to high-ROI channels

---

## 🔍 Key Takeaways

- **TV and Radio** are clearly pulling their weight. 📺📻  
- **Newspaper**? Not so much — cutting spend here and redirecting it improved predicted ROI by **~22%**.
- The final model explained **~90% of variance in sales**, which is solid for real-world media modeling.

---

## 📦 Dataset

I used the well-known [Advertising Dataset](https://www.kaggle.com/datasets/ashydv/advertising-dataset), which includes weekly ad spend across 3 channels and resulting product sales.

---

## 🧰 Tools Used

- Python (Pandas, NumPy)
- Scikit-learn & Statsmodels
- Seaborn, Matplotlib
- Jupyter Notebook

---

## ✍️ What’s Next?

I’d love to take this further by:
- Adding digital marketing channels (e.g. social, influencer)
- Applying adstock or carryover effects to simulate long-term impact
- Using Bayesian MMM for more robust insights

---
