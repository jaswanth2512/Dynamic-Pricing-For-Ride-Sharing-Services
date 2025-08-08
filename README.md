# 🚖 Dynamic Pricing for Ride-Sharing Services

This project explores dynamic pricing prediction in the ride-sharing industry using machine learning techniques. Our goal is to build predictive models that estimate ride fares based on multiple real-world factors like distance, time, traffic, weather, and demand.

## 📌 Problem Statement

Ride-sharing services often rely on dynamic pricing to adjust fares in real-time. However, without a reliable predictive system, prices can seem arbitrary to users and unfair to drivers. This project aims to:

- Predict ride prices using historical ride and weather data.
- Analyze and compare models like Random Forest, XGBoost, and Support Vector Regressor (SVR).
- Evaluate the models using MAE, RMSE, and R² scores.
- Recommend the best model for deployment in real-world pricing systems.


## 📁 Dataset Summaries

### 📌 Dataset 1

**🧾 Features Used:**
- `Trip_Distance_km`
- `Time_of_Day`
- `Day_of_Week`
- `Passenger_Count`
- `Traffic_Conditions`
- `Weather`
- `Base_Fare`
- `Per_Km_Rate`
- `Per_Minute_Rate`
- `Trip_Duration_Minutes`

**🎯 Target:**
- `Trip_Price`

**✅ Best Model:** `Support Vector Regressor (SVR)`

**📌 Reason:**
After applying preprocessing (handling missing values, one-hot encoding, and scaling), SVR achieved the best performance in terms of **MAE**, **RMSE**, and **R²** metrics compared to Random Forest and XGBoost.

---

### 📌 Dataset 2

**🧾 Features Used (after merging ride and weather data):**
- `distance`
- `cab_type`
- `source`
- `destination`
- `surge_multiplier`
- `temp`
- `humidity`
- `clouds`
- `pressure`
- `rain`
- `wind`

**🗑️ Dropped Columns:**
- `id`
- `product_id`
- `time_stamp`
- `name` (non-predictive)

**🎯 Target:**
- `price`

**✅ Best Model:** `Random Forest Regressor`

**📌 Reason:**
Random Forest performed well on this dataset due to its ability to handle complex feature interactions and categorical variables (after encoding). It outperformed SVR and XGBoost in terms of stability and accuracy.

---

### 📌 Dataset 3

**🧾 Features Used:** *(exact column names not specified in the PPT, assumed similar ride data)*
- `distance`
- `duration`
- `weather_conditions`
- `traffic`
- `day_of_week`
- `time_of_day`

**🎯 Target:**
- `price`

**✅ Best Model:** `XGBoost Regressor`

**📌 Reason:**
On this dataset, XGBoost outperformed others due to its strong handling of non-linear relationships and better generalization across unseen ride patterns.

---

## 📊 Evaluation Metrics

All models were evaluated using:

- **Mean Absolute Error (MAE)**
- **Root Mean Squared Error (RMSE)**
- **R² Score**

---


## 📘 Conclusion

- SVR was best for Dataset 1 (well-structured numeric + categorical data).
- Random Forest was best for Dataset 2 (merged ride and weather data).
- XGBoost was best for Dataset 3 (possibly sparse or unbalanced features).

By combining machine learning with real-world features, we show that intelligent dynamic pricing is possible, reliable, and scalable for ride-sharing services.

---

## 📎 License

This project is for educational and academic purposes only.
