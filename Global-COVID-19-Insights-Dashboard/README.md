# 🌍 Global COVID-19 Insights Dashboard

![2](https://github.com/user-attachments/assets/1b261666-d2c8-4740-a7db-3d2664b2cbf1)


## 📊 Project Overview

The **Global COVID-19 Insights Dashboard** is an interactive data visualization project built using **Power BI**. It provides a comprehensive, at-a-glance overview of global COVID-19 statistics, enabling users to explore trends across countries in terms of active cases, recoveries, and fatalities.

This dashboard is designed to assist health researchers, policy analysts, and the public in understanding the impact and spread of the pandemic worldwide through a clear, data-driven interface.

---

## 🧠 Objectives

- Visualize global COVID-19 data in an interactive and intuitive format.
- Provide key health metrics such as active cases, total cases, recoveries, and deaths.
- Enable country-level analysis and comparisons.
- Demonstrate the use of DAX, measures, and disconnected tables in Power BI.
- Promote insights through compelling visual storytelling.

---

## 📁 Files Included

- `Global COVID-19 Insights Dashboard.pbix` — The main Power BI dashboard file.
- `README.md` — Project documentation (this file).

---

## 🛠 Tools & Technologies

- **Power BI Desktop**
- **DAX (Data Analysis Expressions)**
- Power BI visuals (bar chart, pie chart, map, table)
- Custom formatting and interactivity

---

## 🔍 Key Features

### 🧾 Summary Metrics
- Total Cases
- Active Cases
- Recovered Cases
- Deaths
- Recovery Rate
- Death Rate

### 📊 Visualizations
- **Cases by Status** (Pie Chart)
- **Total Cases by Country** (Bar Chart)
- **Recovered Cases by Country** (Bar Chart)
- **Total Deaths by Country** (Map)
- **Active Cases by Country** (Scrollable Table)

### 🌐 Interactivity
- Dynamic country filter
- Disconnected status slicer table
- DAX-based measure switching

---

## 📐 Data Modeling

- Measures for each status type (`Active`, `Recovered`, `Deaths`)
- Disconnected `Status Table` to build a flexible pie chart
- `SWITCH()` and `SELECTEDVALUE()` functions used to dynamically calculate values based on selected status
- No direct relationship needed between status and main data table

---

## 🧮 Key DAX Measures

```DAX
Total Active = SUM('Table'[Active Cases])
Total Recovered = SUM('Table'[Recovered Cases])
Total Deaths = SUM('Table'[Deaths])
Total All Status = [Total Active] + [Total Recovered] + [Total Deaths]
Cases by Status = 
    SWITCH(
        SELECTEDVALUE('Status Table'[Status]),
        "Active", [Total Active],
        "Recovered", [Total Recovered],
        "Deaths", [Total Deaths]
    )

## 🚀 Getting Started

To explore the dashboard:

1. Clone the repository or download the `.pbix` file.
2. Open the file in **Power BI Desktop**.
3. Refresh data if needed (ensure dataset paths or mock data are available).
4. Interact with the dashboard using filters and slicers.
