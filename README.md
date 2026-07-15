# 🌍 Human Development Index (HDI) Predictor

A hybrid deep-learning system that predicts a country's **Human Development Index score** and classifies it into a development tier — **Low, Medium, High, or Very High** — from key socio-economic indicators, served through a live, interactive web dashboard.

🔗 **Live App:** [https://hdi-webapp.onrender.com](https://hdi-webapp.onrender.com)
*(Free-tier hosting — first load may take 30–50 seconds to wake up.)*

---

## 📌 Overview

Official HDI computation requires manually combining normalized health, education, and income sub-indices through a fixed UNDP formula — slow and inaccessible for quick, exploratory, or "what-if" analysis. This project replaces that manual process with a trained neural network that learns the indicator-to-HDI relationship directly from historical data, and exposes it through a simple web form for instant predictions.

**Team:**
- Nimmakayala Venkata Satheesh Kumar — Team Lead
- Cherukuri Sailaja Kiranmai — Group Member

**Team ID:** AIML-HDI-2026

---

## ⚙️ Tech Stack

| Layer | Technology |
|---|---|
| Data Processing | cuDF (RAPIDS GPU DataFrame), Pandas, NumPy |
| Model Development | PyTorch (dual-branch neural network, AdamW optimizer) |
| Evaluation & Metrics | scikit-learn (classification report, confusion matrix, ROC-AUC) |
| Visualization | Matplotlib, Seaborn |
| Backend | Flask, Gunicorn |
| Frontend | HTML5, CSS3 (Jinja2 templating) |
| Deployment | Render (production), LocalTunnel (development/demo) |
| Dataset | [Kaggle — Human Development Index (Full)](https://www.kaggle.com/datasets/iamsouravbanerjee/human-development-index-dataset) |

---

## 📊 Model Performance

| Metric | Value |
|---|---|
| Mean Absolute Error (MAE) | 0.0264 |
| Root Mean Squared Error (RMSE) | 0.0311 |
| Overall Classification Accuracy | 83% |
| Macro Avg F1-score | 0.83 |

---

## 🗂️ Repository Structure

```
├── 1. Brainstorming & Ideation/       # Problem statements, empathy map, idea prioritization
├── 2. Requirement Analysis/           # Customer journey, solution requirements, data flow, tech stack
├── 3. Project Design Phase/           # Problem-solution fit, proposed solution, architecture
├── 4. Project Planning Phase/         # Sprint planning, backlog
├── 5. Project Development Phase/      # Dataset, training notebook, Flask app code
├── 6. Project Testing/                # Functional & performance testing
├── 7. Project Documentation/          # Final project report
└── 8. Project Demonstration/          # Demo video / screenshots
```

---

## 🚀 Running Locally

```bash
git clone https://github.com/sailajakiranmai06/Human-Development-Index-Predictor.git
cd Human-Development-Index-Predictor/5.\ Project\ Development\ Phase

pip install -r requirements.txt
python app.py
```

The app will start locally at `http://127.0.0.1:5000`.

---

## 🔮 How It Works

1. User enters **Life Expectancy**, **Expected Years of Schooling**, and **GNI per Capita** into the web form
2. Inputs are scaled and passed through a **dual-branch neural network** — one branch for core UNDP indicators, one for auxiliary features
3. The model outputs a predicted **HDI score** and a **development tier** (Low / Medium / High / Very High)
4. Result is displayed instantly with a color-coded tier badge

---

## 🔭 Future Scope

- Replace hard tier thresholds with a learned, soft classification head
- Incorporate multi-year historical data with temporal modeling (LSTM/Transformer) for trend forecasting
- Move from session-based hosting to a persistent, always-on deployment
- Add explainability (e.g., SHAP values) to show which indicators drove a given prediction
