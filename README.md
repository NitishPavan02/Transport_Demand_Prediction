# 🚌 Nairobi Transport Demand Prediction

## 📌 Project Overview
This project predicts the number of seats Mobiticket can expect to sell for each bus ride operating from towns northwest of Nairobi towards Lake Victoria, Kenya. Built as a Data Science Capstone Project using real ticket booking data with 51,000+ records.

---

## 🎯 Problem Statement
Given ride details such as origin town, departure time, date, car type, and payment method — predict the **number of tickets sold per ride** to help optimize fleet allocation and scheduling.

---

## 📂 Dataset
| Feature | Description |
|---|---|
| `ride_id` | Unique ID for each ride |
| `seat_number` | Seat booked by passenger |
| `payment_method` | Mpesa or Cash |
| `travel_date` | Date of travel |
| `travel_time` | Departure time |
| `travel_from` | Origin town (17 towns) |
| `travel_to` | Destination (Nairobi) |
| `car_type` | Bus (49 seats) or Shuttle (11 seats) |
| `max_capacity` | Maximum seat capacity |

- **Total Records:** 51,645 ticket-level rows
- **After Aggregation:** Ride-level dataset for modeling

---

## 🔧 Project Pipeline

```
Data Loading → EDA → Feature Engineering → Preprocessing → Modeling → Evaluation → Explainability
```

### 1️⃣ Exploratory Data Analysis
- Payment method & car type distributions
- Tickets sold per origin town
- Booking patterns by hour and day of week
- Target variable distribution

### 2️⃣ Feature Engineering
| New Feature | Description |
|---|---|
| `day_of_week` | Day extracted from travel date |
| `month` | Month of travel |
| `is_weekend` | 1 if Saturday or Sunday |
| `travel_hour` | Hour of departure |
| `time_of_day` | Morning / Afternoon / Evening bin |
| `occupancy_rate` | Tickets sold / max capacity |

### 3️⃣ Models Trained
| Model | Type |
|---|---|
| Linear Regression | Baseline |
| Ridge Regression | Regularized Linear |
| Lasso Regression | Regularized Linear |
| Decision Tree | Tree-based |
| Random Forest | Ensemble ⭐ Best |
| Gradient Boosting | Ensemble |

### 4️⃣ Best Model — Tuned Random Forest
- Hyperparameter tuning using **GridSearchCV**
- Evaluated on MAE, RMSE, and R²
- Feature importance plotted for explainability

---

## 📊 Visualizations
| Chart | Insight |
|---|---|
| `payment_cartype_distribution.png` | Mpesa dominates payments |
| `tickets_per_town.png` | Kisii & Migori are busiest routes |
| `bookings_by_hour.png` | Early morning departures most popular |
| `avg_tickets_by_day.png` | Weekend vs weekday demand |
| `correlation_heatmap.png` | Feature relationships |
| `model_comparison.png` | All model performance |
| `feature_importance.png` | Top predictors |
| `actual_vs_predicted.png` | Model accuracy visualization |

---

## 💡 Key Business Insights
1. **Mpesa dominates** — 80%+ tickets purchased digitally
2. **Kisii, Migori & Rongo** generate highest ticket volumes
3. **Early morning (5–8 AM)** is peak departure time
4. **Buses outperform shuttles** in demand volume
5. **Weekends show different demand** patterns vs weekdays

## 📢 Business Recommendations
- Deploy more buses on Kisii & Migori routes during early mornings
- Offer discounts on low-demand routes to balance occupancy
- Incentivize Mpesa payments to reduce cash handling costs
- Adjust departure times to avoid Nairobi peak traffic arrivals

---

## 🛠️ Tech Stack
![Python](https://img.shields.io/badge/Python-3.10-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.0-green)
![Scikit--learn](https://img.shields.io/badge/Scikit--learn-1.3-orange)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7-red)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12-purple)
![Google Colab](https://img.shields.io/badge/Google-Colab-yellow)

---

## 🚀 How to Run
1. Clone the repo
```bash
git clone https://github.com/NitishPavan02/Transport_Demand_Prediction.git
```
2. Open `Nairobi_Transport_Demand_Prediction_clean.ipynb` in Google Colab
3. Upload `train_revised.csv` when prompted
4. Run all cells — **Runtime → Run All**

---

## 👤 Author
**Nitish Pavan**
- GitHub: [@NitishPavan02](https://github.com/NitishPavan02)
- Email: scs723582@gmail.com
