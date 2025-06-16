# 🚲 Citi Bike Machine Learning Analysis

Citi Bike, New York City's largest bike-sharing system, plays a crucial role in promoting sustainable urban transportation. By analyzing historical trip data, this project aims to uncover usage patterns that can help optimize operations, enhance user experience, and support infrastructure planning.

## 📊 Project Objectives

* Predict **trip duration** based on user and trip features
* Classify riders as **casual users vs members**
* Cluster **stations** by usage and location
* **Forecast ride demand** over time
* Evaluate a **neural network** for predictive performance

---

## ⚙️ Baseline Models

To establish benchmarks, we implemented two simple models:

* **Linear Regression**: Predicted trip duration using features like start/end stations, bike type, trip time, and location.

  * **R² Score:** 0.0148
* **Logistic Regression**: Classified users as members or casual riders.

  * **Accuracy:** 81%

These models lacked complexity and tuning but served as starting points for deeper exploration.

---

## 🌲 Random Forest Regression

To improve trip duration prediction, we implemented a **Random Forest Regressor** with hyperparameter tuning via **randomized search**.

* **Optimized Parameters:** `n_estimators`, `max_depth`, `min_samples_split`, `min_samples_leaf`, `max_features`
* **Performance:**

  * **RMSE:** Reduced from 7.32 → **4.67**
  * **R² Score:** Increased from 0.0148 → **0.59**

The tuned model captured non-linear relationships significantly better than the baseline.

---

## 📍 Station Clustering

We used **K-Means Clustering** to group Citi Bike stations based on geographic location:

* Initial experiment: `n=5` clusters

  * Resulted in significant overlap between clusters
* Refined experiment: `n=3` clusters

  * One dominant cluster centered in **Midtown East**, a high-traffic area

Using **latitude and longitude**, we visualized station groupings to support service area planning and bike redistribution strategies.

---

## 📈 Time Series Forecasting

To understand **seasonal ride trends**, we applied:

* **ARIMA**
* **SARIMA** (seasonal component)

**Key insights:**

* **Seasonal peaks** in spring/summer, dips in winter
* **Weekday vs weekend** usage patterns (commuters vs leisure riders)
* Clear drop on **holidays** (e.g., Christmas Day)
* **SARIMA** outperformed ARIMA in capturing periodic trends

These models can help Citi Bike forecast demand, optimize fleet availability, and plan maintenance cycles.

---

## 🧠 Neural Network Model

We developed a simple feedforward neural network using PyTorch to predict trip duration.

* **Training loss** decreased steadily
* **Test loss** plateaued and fluctuated after \~6 epochs
* **Unexpected result:** Test loss was consistently **lower** than training loss
* **R² Score (test set):** **6.1%**

This underperformance suggests potential overfitting or model/data mismatches, calling for more advanced architectures or feature engineering.

---

## 🛠️ Tools & Technologies

* **Python** (Pandas, NumPy, Matplotlib, Seaborn)
* **Scikit-learn** (Linear/Logistic Regression, Random Forest, K-Means)
* **Statsmodels** (ARIMA, SARIMA)
* **PyTorch** (Neural Network)
* **Jupyter Notebook** for experimentation and visualization

---

## 📌 Conclusion

This end-to-end analysis showcases how traditional ML, clustering, time-series models, and deep learning can be used to gain actionable insights into urban mobility systems like Citi Bike. From predicting demand to understanding rider behavior, the results inform smarter, data-driven decisions for city planners and service providers alike.
