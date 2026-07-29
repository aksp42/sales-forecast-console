# 📈 Sales Prediction using Python

An end-to-end machine learning project that predicts product sales based on advertising spend across **TV, Radio, and Newspaper** channels — built as **Task 4** of the CodeAlpha Data Science Internship.

The project goes beyond a notebook: it ships with a fully interactive, in-browser **Sales Console** dashboard where you can drag ad-spend sliders and watch the trained model forecast sales live, with real-time channel-impact analysis.

---

## 🔴 Live Demo

**[Sales Console — Advertising Forecast Model](./sales_console.html)**

Open `sales_console.html` in any browser — no server, no dependencies. The trained Random Forest model runs entirely client-side in JavaScript.

---

## 🧠 Project Overview

The goal is to predict future sales based on advertising spend, target segment, and platform, and to translate that model into actionable marketing insight.

**Workflow:**
1. **Data Cleaning & Transformation** — handled missing values, checked distributions, and prepared the advertising dataset for modeling.
2. **Feature Engineering** — engineered `total spend` and a `TV × Radio` interaction term on top of the raw channel spends to capture cross-channel synergy effects.
3. **Model Building** — trained and compared regression models to forecast sales from ad spend.
4. **Model Selection** — selected a **Random Forest Regressor (300 trees)** as the final model based on performance.
5. **Impact Analysis** — quantified how a marginal increase in spend on each channel moves predicted sales.
6. **Deployment** — exported the trained model into a lightweight in-browser inference engine and built an interactive dashboard around it.

---

## ✨ Features

- 🎚️ **Live mixing-console UI** — TV, Radio, and Newspaper spend sliders with LED-style level meters
- 🔮 **Real-time inference** — predictions computed instantly in-browser via a JS port of the trained Random Forest
- 📊 **Sensitivity analysis** — per-channel bar chart showing sales lift from a +10% spend bump on each channel
- 💡 **Auto-generated insights** — plain-English narrative on which channel is the strongest/weakest lever at the current spend mix
- 💰 **Spend efficiency readout** — units of sales generated per $1k spent
- 📱 Fully responsive, dark-themed, dependency-free single HTML file

---

## 🗂️ Project Structure

```
Sales-Prediction-CodeAlpha/
├── Advertising.csv                   # Dataset: TV, Radio, Newspaper spend vs Sales
├── Sales_Prediction_Advanced.ipynb   # Full analysis: EDA, feature engineering, modeling
├── sales_prediction_model.pkl        # Serialized trained model (pickle)
├── sales_console.html                # Interactive in-browser forecasting dashboard
└── README.md
```

---

## 📊 Dataset

The dataset (`Advertising.csv`) contains advertising budgets (in $ thousands) across three channels along with the resulting product sales:

| Column | Description |
|---|---|
| `TV` | Advertising spend on TV (in $k) |
| `Radio` | Advertising spend on Radio (in $k) |
| `Newspaper` | Advertising spend on Newspaper (in $k) |
| `Sales` | Units of product sold (target variable) |

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| Data Handling | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Modeling | Scikit-learn (Random Forest Regressor) |
| Environment | Jupyter Notebook |
| Dashboard | HTML, CSS, Vanilla JavaScript |

---

## 🌲 Model

- **Algorithm:** Random Forest Regressor — 300 estimators
- **Input features:** `TV`, `Radio`, `Newspaper`, `Total Spend` (engineered), `TV × Radio` interaction (engineered)
- **Target:** `Sales`
- The trained model is serialized to `sales_prediction_model.pkl` and separately exported as a compact tree-array representation embedded directly in `sales_console.html`, allowing predictions to run without a backend.

---

## 🚀 Getting Started

### Run the notebook
```bash
git clone https://github.com/<your-username>/Sales-Prediction-CodeAlpha.git
cd Sales-Prediction-CodeAlpha
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
jupyter notebook Sales_Prediction_Advanced.ipynb
```

### Run the dashboard
No setup required — just open `sales_console.html` directly in your browser, or serve it locally:
```bash
python -m http.server 8000
# then visit http://localhost:8000/sales_console.html
```

---

## 📈 Key Insights

- Advertising spend on **TV** and **Radio** consistently drives the strongest lift in sales, with a measurable synergy effect between the two.
- **Newspaper** spend shows comparatively weaker/flatter returns at most spend levels.
- Businesses can use the sensitivity panel in the dashboard to identify where the **next marketing dollar** will have the highest impact, before committing budget.

---

## 🙌 Acknowledgements

Built as part of the **[CodeAlpha](https://www.codealpha.tech/)** Data Science Internship — Task 4: Sales Prediction using Python.

---

## 👩‍💻 Developed By

**Akanksha Singh** - https://www.linkedin.com/in/akanksha-singh-4715a0351/ 

Video of the project : https://www.linkedin.com/feed/update/urn:li:activity:7488282143182221312/

📜 License
This project is open source and available under the [MIT License](LICENSE).

---
