# OLAP Spotify Music Trend Analytics — Data Warehouse and OLAP Project

This repository contains the coursework project for the Data Warehouse and OLAP subject at the University of Information Technology (UIT) — VNU-HCM. The project focuses on analyzing Spotify Trending Songs data using Data Warehouse architecture, ETL processing, OLAP cube modeling, and analytical reporting.

The goal of the project is to transform raw Spotify chart data into structured warehouse data and enable multi-dimensional analytical exploration to support trend analysis and insight discovery.

---

## Project Overview

This project implements an end-to-end analytical workflow for Spotify trending songs across multiple countries. The workflow includes dataset preprocessing, warehouse schema construction, ETL pipeline development with SSIS, OLAP cube creation in SSAS, trend exploration through MDX and Pivot browsing, and dashboard-based visualization.

The analysis supports ranking-pattern exploration, time-based trend monitoring, and country-level performance comparison.

---

## Objectives

- Design a Data Warehouse for Spotify song ranking and trend analytics  
- Build an ETL pipeline to transform and load structured data into the warehouse  
- Develop OLAP cubes to enable multi-dimensional analysis (song, artist, time, country)  
- Perform ranking and trend exploration using MDX queries and Pivot browsing  
- Create analytical dashboards to summarize key insights and performance indicators  
-  Extend analytical results with a small **Data Mining component** for
  popularity-level classification (Low / Medium / Hit) based on audio,
  temporal, and geographic features  
---

## Technologies Used

### Data Platform and Warehouse
- Microsoft SQL Server  

### ETL
- SQL Server Integration Services (SSIS)

### OLAP and Analytics
- SQL Server Analysis Services (SSAS)  
- MDX queries  
- Excel Pivot exploration

### Visualization
- Power BI  
- Looker Studio 

### Data Processing / Mining
- Python (Jupyter Notebook)
- pandas-based analytical exploration

---

## Source Dataset

Public dataset used in this project:

Top Spotify Songs in 73 Countries (Daily Updated) — Kaggle  
https://www.kaggle.com/datasets/asaniczka/top-spotify-songs-in-73-countries-daily-updated 

---

## Artifacts Produced (Processing & Analytics Pipeline)

- **Preprocessed dataset —  [`final_data.rar`](Data/final_data.rar)**

  - Raw Spotify chart data was cleaned and standardized
  - Removed special characters and inconsistent textual fields
  - Filtered to retain only **Asian countries / regions** for focused analysis
  - Exported as the final dataset used in the warehouse pipeline

- **Snowflake-style Data Warehouse schema**
  - ![Schema](Images/snowflake.png)
  - Fact table for ranking and streaming metrics
  - Dimension tables for song, artist, album, country, date, and popularity group
  - Schema designed based on analytical and OLAP reporting requirements

- **ETL pipeline (SSIS)**
  - ![ETL](Images/etl.png)
  - Loads the preprocessed dataset into the Data Warehouse
  - Performs data transformation, mapping, and surrogate-key handling
  - Populates fact and dimension tables consistently

- **OLAP cube (SSAS)**
  - Supports multi-dimensional exploration across time, song, artist, and geography
  - Enables ranking-trend analysis and regional performance comparison

### MDX Query 
- A collection of MDX scripts used for:
  - trend exploration
  - ranking-movement analysis
  - time-based and region-based comparisons
- Queries are executed directly on the SSAS cube to support analytical reasoning.

### Dashboard

![Dashboard](Images/dashboard.png)

### Data Mining Component

In addition to OLAP analysis, the project includes a small Data Mining task formulated as a multi-class classification problem.

The objective is to predict the popularity level of a song based on audio features, time-related attributes, and chart geography.

- Input features:
  - audio features (numeric attributes derived from Spotify metadata)
  - time attributes (date, period, temporal grouping)
  - geographic attributes (country / region)

- Target variable:
  - `popularity_class`, derived from the continuous popularity score
  - discretized into three levels:
    - Low (0–60)  
    - Medium (61–80)  
    - Hit (81–100)

The mining workflow includes preprocessing, feature transformation, popularity discretization, train/test splitting, and model evaluation using accuracy and basic classification metrics.  
This component illustrates how analytical results from the warehouse can be extended into predictive tasks to support decision-support use cases.

---

## Repository Structure

- **Data/**
  - `final_data.rar` — compressed dataset used for ETL

- **Document/**: Project documentation

- **Images/**
  - `dashboard.png` — Power BI dashboard screenshot  
  - `snowflake.png` — data warehouse schema diagram

- **Source/**
  - **Data Mining Project/** — Mining notebook
  - **Excel Pivot file/** — Pivot exploration queries and exports  
  - **SSAS Project/** — OLAP cube (SSAS)  
  - **SSIS Project/** — ETL pipeline (SSIS)  
  - **SSRS Project/** — Power BI and Locker Studio
## Author

Student: **Đặng Quốc Cường**  
Institution: **University of Information Technology (UIT), VNU-HCM**  
Course: **Data Warehouse and OLAP**

---

