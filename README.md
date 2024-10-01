# Predicting Race outcomes in Formula-1



Hello, I’m Ravi Solanki, and I’ve undertaken this project as part of my Bachelor of Science in Mathematics and Statistics at Brock University. The goal was to predict Formula-1 race outcomes using advanced data science techniques. I leveraged telemetry data from the FastF1 API, explored machine learning models, and performed ETL processes to convert raw data into actionable insights.

Project Overview

In Formula-1, milliseconds count, and data science can make a world of difference. This project focuses on utilizing race telemetry data to predict drivers’ performance based on various metrics like speed, throttle, RPM, and brake application. Through machine learning models such as Linear Regression and Random Forest, I aimed to develop reliable predictions for race outcomes.

Data Extraction and ETL

To begin, I extracted raw telemetry data using the FastF1 API, which provides in-depth information on each lap of a Formula-1 race. I also scraped race points and standings from Formula 1’s official website. This process involved:

Extract: I pulled detailed telemetry data (speed, throttle, RPM, and brake) lap by lap for each race, in addition to gathering driver performance data.
Transform: The raw data was cleaned and transformed into structured datasets. I handled missing values, standardized variables, and aggregated data at the lap, race, and season levels.
Load: The cleaned datasets were loaded into data frames for easy access and further analysis, including machine learning model development.

Example Code for Data Extraction:

import fastf1
fastf1.Cache.enable_cache('cache')

# Extract session data for a specific race
session = fastf1.get_session(2022, 'Monza', 'R')
session.load()

# Extract lap data for a specific driver
laps = session.laps.pick_driver('VER')


Data Analysis and Feature Engineering

I conducted Exploratory Data Analysis (EDA) on key telemetry variables to identify trends and patterns across races. I aggregated the data into both lap-wise and race-wise subsets to capture insights across different scales.

For example, the function summarize_lap_data() calculates the average speed, throttle, RPM, and brake usage for each lap, which helps analyze driver performance fluctuations throughout the race:

def summarize_lap_data(lap):
    avg_speed = lap['Speed'].mean()
    avg_throttle = lap['Throttle'].mean()
    avg_rpm = lap['RPM'].mean()
    return avg_speed, avg_throttle, avg_rpm



Machine Learning Models

Linear Regression

Linear regression was applied to explore the relationship between telemetry variables and race outcomes (i.e., driver points). Although it provided a baseline model, the results showed that race outcomes are influenced by additional factors that were not captured by this model alone.

from sklearn.linear_model import LinearRegression
model = LinearRegression()

# Preparing the data
X = lap_summary[['Average_Speed', 'Average_RPM', 'Throttle']]
y = lap_summary['Points']

# Fitting the model
model.fit(X, y)

Random Forest Regression

The Random Forest model was introduced to capture non-linear relationships and handle high-dimensional data. This model outperformed linear regression but still indicated the need for more features such as tire data and weather conditions.

from sklearn.ensemble import RandomForestRegressor

# Training the Random Forest model
rf_model = RandomForestRegressor(n_estimators=100, max_depth=8)
rf_model.fit(X_train, y_train)


Clustering Analysis

To further understand the drivers’ behavior, I employed K-means Clustering to group drivers based on their telemetry data. Silhouette analysis was used to evaluate the quality of the clusters. The clustering helped identify patterns that could inform strategy adjustments and performance insights:

from sklearn.cluster import KMeans
kmeans = KMeans(n_clusters=2)
kmeans.fit(X)

The analysis revealed two distinct clusters in driver behavior, confirming that performance varies significantly based on telemetry data.

Results and Reflections

Model Performance: The Random Forest model achieved modest success in predicting driver points, but there is potential for improvement by incorporating additional race conditions such as weather, tire choices, and pit stop strategies.
Cluster Insights: Clustering analysis uncovered two primary performance profiles, suggesting that some drivers are consistently better under specific race conditions.

Future Enhancements

To improve prediction accuracy, I plan to:

Integrate Additional Features: Include tire data, weather conditions, and track details to capture more variables that influence race outcomes.
Advanced Modeling: Experiment with time series analysis and more complex models like XGBoost.
Optimization: Enhance the ETL process to ensure cleaner, higher-quality data.

Conclusion

This project highlights the potential of data science in Formula 1 racing. By combining machine learning with rigorous data analysis, we can uncover actionable insights that can influence race strategy and performance optimization. The project is a great example of how data-driven decision-making can enhance a sport driven by fractions of a second.

For a deeper dive into the methodology and complete analysis, check out the full report, 'Honors_Project'
