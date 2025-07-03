# 🎲 South African Lotto Predictor Project

This project aims to analyze historical Lotto draw data from the South African National Lottery to detect patterns, biases, or anomalies that can be used to simulate or predict future outcomes.

---

## 📁 Project Structure

```bash
lotto_predictor_project/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   └── eda.ipynb
├── scripts/
│   ├── fetch_historical_draws.py
│   ├── clean_historical_draws.py
│   ├── randomness_test.py
│   └── bayesian_simulator.py
├── models/
│   └── model_v1.pth  # Placeholder for future PyTorch models
├── schedule_job.py
├── requirements.txt
└── README.md
```

---

## 🧰 Step 1: Environment Setup

### 1.1. Create and activate virtual environment

```bash
python3 -m venv venv
source venv/bin/activate  # or .\venv\Scripts\activate on Windows
```

### 1.2. Install requirements

```bash
pip install -r requirements.txt
```

---

## 🧹 Step 2: Fetch and Preprocess Historical Data

### 2.1. Scrape historical lotto draw data

```bash
python scripts/fetch_historical_draws.py
```

💡 This script saves raw HTML or JSON data to `data/raw/draws_raw.csv`.

### 2.2. Clean and format the data

```bash
python scripts/clean_historical_draws.py
```

✅ Produces a `clean_draws.csv` in `data/processed/` containing columns:

- Date  
- Draw Number  
- Numbers (list of 6 integers)  
- Bonus Number  

---

## 🧪 Step 3: Test for Randomness or Bias

### 3.1. Run statistical randomness tests

```bash
python scripts/randomness_test.py
```

📊 Tests include:

- Chi-square distribution test  
- Runs test  
- Frequency test  
- Entropy test  

🎯 Determines whether the draw process is **cryptographically random** or **mimics randomness**.

---

## 🧠 Step 4: Run Bayesian Simulation

### 4.1. Launch simulator based on past frequency & probability

```bash
python scripts/bayesian_simulator.py
```

🔁 Simulates thousands of draws and suggests most probable combinations based on posterior probabilities.

---

## 📅 Step 5: Automate Predictions for 2 Weekly Draws

### 5.1. Scheduled script for draw predictions

```bash
python schedule_job.py
```

🗓 Pulls latest draws, updates the model, and outputs predicted numbers for upcoming:

- Wednesday Draw  
- Saturday Draw  

---

## 📊 Step 6: Explore & Visualize (Jupyter)

```bash
jupyter notebook notebooks/eda.ipynb
```

🔍 Use this for plotting distributions, frequencies, or running extra analytics.

---

## 🧪 Tests & Keepers

Tests you SHOULD KEEP as part of the system:

- `randomness_test.py`: Key in determining if modeling is even viable  
- `bayesian_simulator.py`: Core modeling logic and recommendation engine

---

## 📈 Future Upgrades (Optional)

- [ ] Streamlit Dashboard UI  
- [ ] Live API feed for real-time draws  
- [ ] PyTorch deep learning modeling  
- [ ] CI/CD for model retraining  
- [ ] Dockerization  

---

## 📬 Contact

Project maintained by Thatoyaka Dimakatso Malope for research and statistical modeling of Lotto data.
