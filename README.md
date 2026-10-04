# 🏢 Smart Building Energy Intelligence

An end-to-end Business Intelligence project for analyzing energy
performance across a portfolio of smart buildings.

![Executive Dashboard](executive-overview.png)

## 🎯 Business Problem

Building and energy managers need to understand:

- Which buildings consume the most electricity?
- When does peak consumption occur?
- How does consumption vary by building type?
- How does weather relate to energy demand?
- Which buildings show unusual consumption behavior?

## 🛠️ Tech Stack

- Power BI
- Power Query
- DAX
- Dimensional Data Modeling
- ETL
- Data Visualization

## 🔄 Data Preparation & ETL

The project starts with building metadata, hourly electricity
measurements and weather data.

Power Query was used for:

- Data profiling
- Filtering relevant buildings
- Data-type validation
- Reshaping electricity data
- Unpivoting wide meter data
- Date and hour extraction
- Performance optimization

## ⚡ ETL Performance Optimization

The first implementation performed the unpivot operation before
reducing the electricity dataset.

This generated approximately 26.8 million intermediate rows and
significantly increased processing time.

The pipeline was redesigned to select only the relevant building
columns before unpivoting.

This reduced unnecessary processing and improved refresh performance.

## 🗂️ Data Model

The analytical model contains:

- Dim_Building
- Dim_Date
- Fact_electricity
- Fact_weather

The model uses one-to-many relationships between dimensions and
fact tables.

## 📊 Dashboard

The Executive Overview includes:

- Total Electricity
- Average Electricity
- Peak Electricity
- Building Count
- Average Temperature
- Energy Trend
- 24H Load Profile
- Energy by Building Type
- Energy × Weather
- Efficiency Watchlist

## 🔎 Building Detail

Users can drill from the portfolio overview into an individual
building to analyze:

- Monthly energy profile
- 24-hour load behavior
- Peak and average consumption
- Electricity per square meter
- Building characteristics
- Weather context
- Energy Health

![Building Detail](building-detail.png)

## 🚨 Energy Health Monitoring

The project includes baseline-based anomaly monitoring.

Historical electricity behavior is used to calculate expected
consumption for a building/hour. Actual consumption is compared
with this baseline and classified as:

- 🟢 Normal
- 🟠 Warning
- 🔴 Anomaly

This is a rule/baseline-based analytical feature and is not
presented as a trained machine-learning model.

## 💡 Key Learning

The project reinforced an important principle:

> Good Business Intelligence starts before the dashboard — with
> understanding the data, designing an efficient ETL pipeline,
> building a reliable model and translating business questions
> into useful analysis.
