🚖 Taxi Rides Analysis - Azure Fabric Project

This project showcases an end-to-end data analytics workflow using **Microsoft Azure Fabric**, focusing on visualising and analysing taxi ride data. The project demonstrates data exploration, SQL querying, and inte!
ractive visual reporting.

![10c5852d-0918-443d-9186-4268f370c046](https://github.com/user-attachments/assets/e8a3d273-e9b6-4eee-8676-868bb7eceef3)


## 📊 Objective

To analyse taxi ride patterns over time, identifying trends in passenger volume by pickup datetime and presenting the results through clear, interactive charts using Microsoft Fabric tools.

## 🧩 Tools & Technologies

- **Microsoft Azure SQL Database**
- **Azure Fabric Lakehouse**
- **SQL Query Editor (Preview)**
- **OneLake Explorer**
- **Fabric Visualisation Reports**
- **Semantic Models**

## 📁 Dataset

The dataset used for this project includes the following key fields:
- `pepPickupDatetime` – Pickup timestamp for each ride
- `passengerCount` – Number of passengers per trip

The data is stored in **OneLake Lakehouse** format and queried via **SQL Analytics Endpoint** before being visualised.

## 🔍 SQL Queries Used

![a8f3365e-c56e-469c-a270-d6fd66acf0f9](https://github.com/user-attachments/assets/040daef9-4319-4e89-ade6-f37173056376)

![d695e021-33cd-4de4-83eb-75fcd17bb2c6](https://github.com/user-attachments/assets/280ff16f-e5c0-43b8-9643-c6c5a642280c)

```sql
SELECT
  pepPickupDatetime,
  SUM(passengerCount) AS TotalPassengers
FROM taxi_rides
GROUP BY pepPickupDatetime
ORDER BY pepPickupDatetime;
```

This query aggregates passenger counts by pickup datetime to prepare the data for time-series analysis.

## 📈 Visualisations

The project includes the following key visual:

### 📌 Line Chart: Passenger Trends Over Time
- **X-axis:** `pepPickupDatetime`
- **Y-axis:** Sum of `passengerCount`
- This visual helps identify high and low demand periods across years.
- Insights include:
  - A sharp increase in passenger counts during 2015–2019
  - Significant drop post-2020 (likely pandemic effect)
  - Outliers and anomalies in data post-2020 to be cleaned

## 💡 Observations

- Data from around 2015–2020 shows expected ride volume and seasonality patterns.
- Post-2020 data includes anomalies and possible timestamp errors (e.g. future dates like 2070).
- Useful for capacity planning, demand forecasting, and service optimisation.

## 📁 Project Structure

```
/TaxiRidesProject
├── Lakehouse: bafti13
│   └── Tables: taxi_rides
├── SQL Queries: Query Editor in Azure
├── Reports: Taxi Rides Report
│   └── Visual: Line chart (pepPickupDatetime vs Sum of passengerCount)
└── Semantic Model: Defined in Fabric for queryable data modelling
```

## 🔒 Access & Permissions

This project is developed and stored within **My Workspace** in Azure Fabric. Reports are securely published and can be shared or exported from the Fabric workspace.

## 📆 Date

**Project Completion:** 30 May 2025  
**Azure Fabric Trial Remaining:** 38 Days (as of last session)

---


> Created 🔥 by **Bafti Çakır**
