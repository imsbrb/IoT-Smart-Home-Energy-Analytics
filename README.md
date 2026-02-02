# IoT Smart Home Energy Analytics 🏠⚡

## Project Overview

This project focuses on building a comprehensive **Data Warehouse and Business Intelligence (BI)** solution to analyze energy consumption patterns in a low-energy house in Belgium. By integrating IoT sensor data (temperature and humidity) with outdoor weather conditions, the system provides actionable insights into what drives energy usage and identifies opportunities for efficiency.

---

## 🛠 Tech Stack

* 
**Database:** PostgreSQL (Data Warehouse) 


* 
**BI Tool:** Power BI 


* 
**Languages:** SQL, DAX 


* 
**ETL Process:** Python/SQL for extraction, cleaning, and transformation 



---

## 📊 Data Architecture

The project utilizes a **Star Schema** design to optimize query performance for multidimensional analysis.

### Schema Components:

* 
**Fact Tables:** `EnergyUsage_Fact` (Measures: Appliances Wh, Lights Wh, Avg Temperature, Avg Humidity).


* 
**Dimension Tables:** `Date_Dim`, `Time_Dim`, `Room_Dim`, and `Weather_Dim`.



---

## 🚀 Performance Optimizations

To handle analytical workloads efficiently, several physical design techniques were implemented and tested:

| Technique | Improvement | Use Case |
| --- | --- | --- |
| **Materialized View** | **99.7%** | Best for high-level monthly dashboard aggregates.

 |
| **Bitmap Simulation** | **99.2%** | Optimized equality filters for low-cardinality columns (e.g., Windspeed).

 |
| **B-Tree Index** | **68.7%** | Accelerated range filters on time-series data.

 |
| **Vertical Partitioning** | N/A | Tested but found unsuitable due to join overhead on this dataset size.

 |

---

## 📈 Key Insights & BI Dashboards

The Power BI dashboard provides a three-level hierarchy of analysis: **Executive KPIs**, **Trend Analysis**, and **Detailed Matrix** views.

### Critical Findings:

* 
**Appliance Dominance:** Appliances account for **96%** of total energy usage, while lighting is negligible (4%).


* 
**Seasonal Peaks:** Consumption peaks during March and April (approx. 420-450 kWh), suggesting high HVAC activity during the spring transition.


* 
**Anomaly Detection:** Identified a significant **23.19% Month-over-Month growth** spike that may indicate device malfunction or seasonal shifts.


* 
**Weather Correlation:** While energy use increases with temperature, the relationship is non-linear, indicating other behavioral factors are at play.



---

## 📂 Project Structure

* 
`/Proposal`: Initial project scope and schema design.


* 
`/ETL`: Scripts for data cleaning and loading.


* 
`/Optimization_Report`: Detailed analysis of indexing and partitioning performance.


* 
`/Dashboard`: Power BI `.pbix` files and insight summaries.



---

