# 🚕 Ola Cab Ride Analysis & Demand Prediction
SQL + Power BI Project

A complete end-to-end data analytics project using SQL for data manipulation and Power BI for dashboarding, insights, and future demand forecasting—focused on optimizing Ola cab ride services.

🧭 Table of Contents
Project Objective

Tech Stack

Data Schema

SQL Analysis

Power BI Dashboard

Insights Derived

Demand Prediction Logic

Key Visuals

How to Use This Project

Future Work

Resources & References

# 🎯 Project Objective
The aim of this project is to analyze historical Ola ride data using SQL queries and build a Power BI dashboard that:

Identifies peak demand zones and hours

Highlights cancellation and no-show patterns

Analyzes driver availability and idle time

Predicts future demand using trend logic

This analysis can help Ola:

Improve driver allocation

Reduce wait times

Forecast operational needs

Monitor KPIs using live dashboards

# 🧰 Tech Stack
Tool	Purpose
SQL	Data cleaning, joins, aggregations
Power BI	Interactive dashboards and reporting
Excel/CSV	Raw data source files (used in import)
DAX	Metrics calculation inside Power BI

🗃️ Data Schema
Assume the following tables in your SQL/BI model:

Table Name	Description
rides	Contains trip_id, timestamp, driver_id, user_id, status, fare, pickup/drop zones
drivers	Basic driver data (experience, location)
users	Rider demographics
locations	Zone-wise geo mapping (lat/long, region)

Key fields:

status = ['Completed', 'Cancelled', 'No-show']

pickup_time, drop_time for duration

pickup_zone, drop_zone to create demand maps

# 📊 Power BI Dashboard
Your .pbix file (shared here):
🔗 Ola Power BI Dashboard (https://github.com/pradeepsingh077/Ola_projects/blob/main/ola%20project.pbix)

Key dashboard pages:

Daily Demand Tracker

Zone-wise Pickup Heatmap

Hourly Ride Trends

Driver Utilization

Cancellation Summary

Forecasted Demand using Time Series

📈 Insights Derived
🕐 Hourly Trend
Demand peaks at 9–11 AM and again at 6–9 PM (commute hours).

Lowest activity during early morning (1–5 AM).

📍 High-Demand Areas
Top pickup zones: Connaught Place, Sector 62, Indirapuram

Top drop zones: Airport, Railway Station, Malls

🔁 Ride Status Summary
Completed: ~85%

Cancelled: ~10%

No-show: ~5%

👨‍✈️ Driver Utilization
Idle hours: 2.3 hrs/day avg

Active drivers per hour tracked via gauge chart

📈 Demand Prediction Logic
Although Power BI doesn’t train ML models directly, we use DAX and time intelligence for demand forecasting:

dax
Copy
Edit
Forecasted Demand = 
CALCULATE(
  AVERAGE(rides[ride_count]),
  DATESINPERIOD(
    rides[pickup_time],
    MAX(rides[pickup_time]),
    -7,
    DAY
  )
)
Or integrate Power BI with Python/R scripts for advanced forecasting (e.g., ARIMA, Prophet).

🖼️ Key Visuals
Include these charts/screenshots:

Heatmap: pickup_zone vs ride_count

Time-series: hourly demand line chart

Pie chart: status-wise distribution

Forecast graph: predicted vs actual

Card KPIs: total rides, avg fare, cancellation %

Example:

(replace with actual image link)

🛠️ How to Use This Project
Download .pbix file → Here

Install Power BI Desktop → Download

Load local data (CSV/Excel/DB) or connect to your SQL server

Refresh visuals or customize filters

Use buttons, slicers, and filters to interact

🔮 Future Work
Integrate Python ML models inside Power BI

Add real-time data stream from Azure/AWS

Track weather impact on rides

Show driver churn and loyalty analytics

Add feedback/sentiment dashboard from rider ratings

📚 Resources & References
Power BI DAX Guide

Power BI GitHub Repo

Ola Dataset Analysis – Medium Blog (add if available)

Research on Ride Forecasting

ProjectPro: Ride Demand Forecast

👤 About the Author
Pradeep Singh

Data Analyst | Python + SQL + Power BI

LinkedIn: https://www.linkedin.com/in/pradeep-singh-585931230/

GitHub: https://github.com/pradeepsingh077

Email: pradeepsingh.psk610@gmail.com
