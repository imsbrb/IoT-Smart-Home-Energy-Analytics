# IoT Smart Home Energy Analytics 🏠⚡

## 1. Project Overview

The **IoT Smart Home Energy Analytics** project implements a complete **Data Warehouse (DW) and Business Intelligence (BI)** solution to analyze and understand energy consumption patterns in a low-energy residential house located in Belgium.

The primary objective of this project is to integrate **IoT sensor data** (indoor temperature and humidity) with **external weather conditions** and historical energy consumption records to uncover key drivers of energy usage. The system supports both high-level executive insights and detailed analytical exploration, enabling data-driven decisions to improve energy efficiency and detect abnormal consumption behavior.

---

## 2. Objectives

* Design a scalable **data warehouse** optimized for analytical workloads
* Integrate heterogeneous data sources (IoT sensors, weather, energy usage)
* Enable multidimensional analysis using a **star schema**
* Optimize query performance using physical design techniques
* Deliver interactive and insightful dashboards using **Power BI**

---

## 3. Technology Stack

### 3.1 Data Storage

* **PostgreSQL** – Central data warehouse for structured analytical data

### 3.2 Business Intelligence

* **Power BI** – Dashboarding, reporting, and interactive data visualization

### 3.3 Programming & Query Languages

* **SQL** – Schema design, transformations, indexing, and analytical queries
* **DAX** – Measures and calculated metrics in Power BI
* **Python** – ETL scripting for data extraction, cleaning, and loading

### 3.4 ETL Approach

* Data extraction from raw IoT and weather datasets
* Data cleansing and transformation using Python and SQL
* Loading curated data into dimension and fact tables

---

## 4. Data Architecture

The project follows a **Star Schema** design to ensure simplicity, performance, and flexibility for analytical queries.

### 4.1 Fact Table

**EnergyUsage_Fact**

Measures stored in the fact table:

* Appliances Energy Consumption (Wh)
* Lights Energy Consumption (Wh)
* Average Indoor Temperature
* Average Indoor Humidity

### 4.2 Dimension Tables

* **Date_Dim** – Calendar attributes (day, month, quarter, year)
* **Time_Dim** – Hourly and time-based analysis
* **Room_Dim** – Room-level granularity within the house
* **Weather_Dim** – Outdoor weather attributes (temperature, humidity, wind speed, etc.)

This schema enables efficient slicing, dicing, drilling, and aggregation across multiple dimensions.

---

## 5. Performance Optimization Techniques

To support fast analytical queries and dashboard responsiveness, several physical optimization techniques were implemented and evaluated.

| Optimization Technique  | Performance Improvement | Description & Use Case                                                                 |
| ----------------------- | ----------------------- | -------------------------------------------------------------------------------------- |
| Materialized Views      | **99.7%**               | Pre-aggregated monthly metrics for executive dashboards                                |
| Bitmap Index Simulation | **99.2%**               | Optimized equality filters on low-cardinality attributes (e.g., wind speed categories) |
| B-Tree Index            | **68.7%**               | Accelerated range-based queries on time-series data                                    |
| Vertical Partitioning   | N/A                     | Tested but discarded due to join overhead on moderate dataset size                     |

The results demonstrate that **pre-aggregation and indexing** significantly enhance performance for BI workloads.

---

## 6. Business Intelligence & Dashboards

The Power BI dashboards are structured into a **three-tier analytical hierarchy**, ensuring accessibility for both technical and non-technical users.

### 6.1 Executive KPI View

* Total energy consumption
* Appliance vs lighting energy distribution
* Month-over-month growth indicators

### 6.2 Trend Analysis View

* Seasonal energy consumption patterns
* Monthly and daily energy usage trends
* Temperature and humidity impact analysis

### 6.3 Detailed Matrix View

* Room-level and time-level energy breakdown
* Cross-dimensional comparisons
* Drill-through analysis for anomaly investigation

---

## 7. Key Analytical Insights

* **Appliance Energy Dominance:** Appliances contribute approximately **96%** of total energy consumption, while lighting accounts for only **4%**.
* **Seasonal Consumption Peaks:** Energy usage peaks during **March and April (420–450 kWh)**, likely due to increased HVAC activity during seasonal transitions.
* **Anomaly Detection:** A significant **23.19% month-over-month increase** was detected, indicating potential equipment malfunction or behavioral changes.
* **Weather Correlation:** Although higher temperatures generally correspond to increased energy use, the relationship is **non-linear**, suggesting strong behavioral and occupancy influences.

---

## 8. Repository Structure

* **/Proposal** – Initial project proposal, objectives, and conceptual schema design
* **/ETL** – Python and SQL scripts for data extraction, transformation, and loading
* **/Optimization_Report** – Detailed benchmarking and performance evaluation of optimization techniques
* **/Dashboard** – Power BI (.pbix) files and summarized analytical insights

---

## 9. Conclusion

This project demonstrates the effective use of **data warehousing, ETL pipelines, performance optimization, and BI analytics** to transform raw IoT data into meaningful insights. The solution highlights how analytical systems can support energy efficiency, anomaly detection, and informed decision-making in smart home environments.

Future enhancements may include real-time streaming analytics, predictive modeling, and automated anomaly alerts.
