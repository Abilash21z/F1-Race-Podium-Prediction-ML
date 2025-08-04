# F1-Race-Podium-Prediction-ML
This project is about predicting F1 Race Podium finisher based on their track history and qualifying stats

# 🏁 F1 Race Time Prediction - 2025 Chinese Grand Prix

This project uses [FastF1](https://github.com/theOehrly/Fast-F1) and a machine learning model to predict the **2025 Chinese Grand Prix race times** based on qualifying performance, using historical race data from the **2024 Chinese GP**.

## 📦 Requirements

Install the necessary Python package:

```bash
pip install fastf1
Other dependencies used (already commonly available with most environments):

pandas

numpy

scikit-learn

📁 Project Structure
Load historical data using FastF1 from the 2024 Chinese GP

Prepare Qualifying data for 2025 (manually entered)

Merge data and map drivers using FastF1 codes

Train ML model using Gradient Boosting Regression

Predict 2025 race times

Rank drivers by predicted time

Evaluate model using Mean Absolute Error (MAE)

🚀 How It Works
Enable FastF1 caching:

python
Copy
Edit
fastf1.Cache.enable_cache("/content/f1_cache")
Load the 2024 Chinese GP race session:

python
Copy
Edit
session_2024 = fastf1.get_session(2024, 'China', 'R')
session_2024.load()
Extract and clean lap time data:

python
Copy
Edit
laps_2024 = session_2024.laps[["Driver", "LapTime"]]
Input 2025 Qualifying Results:

Example:

python
Copy
Edit
{"Driver": "Max Verstappen", "QualifyingTime (s)": 90.817}
Map drivers to FastF1 codes, then merge with historical lap times.

Train the model:

GradientBoostingRegressor is used on qualifying time to predict lap time.

Make predictions and rank the drivers by estimated race time.

Evaluate model with:

python
Copy
Edit
mean_absolute_error(y_test, y_pred)
📊 Sample Output
python-repl
Copy
Edit
Predicted 2025 Chinese GP Results

Position    Driver                  PredictedRaceTime
1           George Russell          104.73 seconds
2           Max Verstappen          105.14 seconds
3           Isack Hadjar            105.17 seconds
...
12          Yuki Tsunoda            111.36 seconds

Model Error (MAE): 10.72 seconds
📌 Notes
Update the 2025 Qualifying Data with official times once available.

FastF1 uses official F1 telemetry and timing data, which may be updated or cached.

Model is based solely on qualifying time → adding more features (e.g., tire strategy, weather) could improve accuracy.

📚 References
FastF1 Docs
scikit-learn Regression
