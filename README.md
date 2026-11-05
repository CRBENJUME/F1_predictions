# 🏎️ F1 Predictions 2026 — Machine Learning Model

Welcome to the **F1 Predictions 2026** repository! This project leverages machine learning, real-time data from the **FastF1 API**, and historical Formula 1 race results to predict race outcomes and driver finish rankings throughout the 2026 season.

---

## 🚀 Project Overview

This repository features a **Gradient Boosting Regressor** built with `scikit-learn` that forecasts final race durations and finishing orders. Key aspects of the setup include:

* **FastF1 API Integration**: Automated fetching of lap-by-lap timing, qualifying deltas, and official race results.
* **Historical Training Base**: Trained on recent multi-season race and qualifying data.
* **Current Season Context**: Incorporates 2026 qualifying session performance to reflect current season pace.
* **Continuous Updates**: Model features and data feeds are iteratively expanded across the 2026 calendar.

---

## 📊 Data Sources

* **FastF1 API**: Primary data pipeline for lap times, session outcomes, and sector metrics.
* **Current Qualifying Data**: Provides starting grid order and single-lap pace metrics as model input.
* **Historical F1 Results**: Cleaned and structured past race datasets used to train the regressor.

---

## 🏁 How It Works

1. **Data Ingestion**: Pulls official session telemetry and classification via FastF1.
2. **Preprocessing & Feature Engineering**: Cleans missing data (DNFs/DNSs), normalizes lap metrics, and calculates starting grid deltas alongside median clean-lap pace indicators.
3. **Model Training**: A `GradientBoostingRegressor` is fit on prior Grand Prix telemetry.
4. **Prediction**: Estimates total race duration in seconds for each driver and sorts them to generate the predicted finishing order.
5. **Evaluation**: Evaluates model precision per race using **Mean Absolute Error (MAE)**.

---

## 🛠️ Dependencies

Ensure you have the following packages installed:

* `fastf1`
* `numpy`
* `pandas`
* `scikit-learn`
* `matplotlib`

Install them in one step:

```bash
pip install fastf1 numpy pandas scikit-learn matplotlib
```
## 📁 File Structure
Scripts follow the official 2026 Formula 1 race calendar sequence:

prediction1.py — Round 1 (e.g., Australian GP)

prediction2.py — Round 2 (e.g., Chinese GP)

prediction3.py — Round 3, and so on.

## 🔧 Usage
Execute the script corresponding to the upcoming Grand Prix weekend:

``` Bash
python3 prediction1.py
```
### Sample Output

```text
==================================================
 PREDICTED FINISHING ORDER: 2026 Australian Grand Prix
==================================================
Pos  | Driver               | Team            | Grid   | Pred Time (s) 
--------------------------------------------------------------------
1    | Charles Leclerc      | Ferrari         | 1      | 5240.120s     
2    | Max Verstappen       | Red Bull Racing | 2      | 5242.450s     
3    | Lando Norris         | McLaren         | 3      | 5245.890s     
--------------------------------------------------------------------
```
## 🔍 Model Error (MAE): 3.22 seconds
==================================================
## 📈 Model Performance
Model accuracy is evaluated using Mean Absolute Error (MAE) calculated against actual race durations. Lower MAE values in seconds indicate more accurate predicted race times.

## 📌 Future Improvements
Integrate track temperature, humidity, and rain probabilities into feature matrices.

Include pit stop strategy windows and tire compound degradation curves.

Explore Deep Learning architectures for non-linear pace modeling.

Social Updates: Follow @mar_antaya on Instagram and TikTok for live prediction releases prior to each 2026 race weekend!

🏎️ Start predicting F1 races like a data scientist! 🚀
