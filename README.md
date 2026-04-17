# 🏨 Hospitality Analytics Dashboard

[![GitHub stars](https://img.shields.io/github/stars/githubgitesh/Hospitality-?style=social)](https://github.com/githubgitesh/Hospitality-/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/githubgitesh/Hospitality-?style=social)](https://github.com/githubgitesh/Hospitality-/network/members)
[![GitHub issues](https://img.shields.io/github/issues/githubgitesh/Hospitality-?style=flat-square)](https://github.com/githubgitesh/Hospitality-/issues)
[![GitHub watchers](https://img.shields.io/github/watchers/githubgitesh/Hospitality-?style=flat-square)](https://github.com/githubgitesh/Hospitality-/watchers)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 📝 Project Overview

This project delivers a **full-cycle Hospitality Analytics solution** — from raw data ingestion to a polished, interactive Power BI dashboard. The goal is to help hotel management understand critical performance metrics and make **data-driven strategic decisions** around revenue, occupancy, and booking behaviour.

The project covers the complete **data analysis lifecycle**: data extraction → cleaning & transformation (Python) → data modeling → DAX measures → interactive visualization (Power BI).

---

## 🎯 Objective

Hotel management often struggles to consolidate data from multiple booking platforms and property types into a coherent view. This project solves that by:

- Tracking and visualising key hospitality KPIs in real time
- Identifying revenue leakage sources such as high cancellation rates
- Comparing performance across room categories, booking channels, and properties
- Revealing seasonal demand trends to inform pricing and staffing strategy

---

## ✨ Key Features

- 📊 **Interactive Power BI Dashboard** — Dynamic slicers and drill-downs for date, hotel, room type, and booking platform
- 📈 **Hospitality KPI Tracking** — Revenue, Occupancy Rate, ADR (Average Daily Rate), and RevPAR (Revenue per Available Room)
- 🧹 **Python-based ETL Pipeline** — Data cleaning and transformation using Pandas and NumPy before loading into Power BI
- 🗂️ **Star Schema Data Model** — Optimised fact and dimension tables for fast query performance
- 📐 **DAX Calculated Measures** — Custom measures for all KPIs, week-over-week trends, and realization percentages
- 🔍 **Booking Platform Analysis** — Channel-wise revenue comparison to identify high-performing sources
- 📅 **Weekly Trend Analysis** — Occupancy, ADR, and RevPAR trends to detect seasonal patterns
- 🏢 **Property-Level Performance Table** — Granular breakdown including cancellation rates and realization %

---

## 📊 Dashboard Highlights & Insights

After analysing the data, the following key business insights were derived:

| Insight | Finding |
|---|---|
| 🏅 Top Revenue Category | Luxury room category contributes the highest share of total revenue |
| 📉 Cancellation Impact | ~25% cancellation rate significantly impacts net revenue |
| 📆 Demand Patterns | Occupancy shows weekly fluctuations, indicating clear seasonal demand cycles |
| 🌐 Best Booking Channel | Certain booking platforms consistently outperform others in both volume and revenue |
| 🏨 Property Performance | Significant variance in realization % across properties, signalling operational improvement opportunities |

### Dashboard Visuals Include:
- Overall KPI cards — Total Revenue, Occupancy %, ADR, RevPAR
- Revenue split by room category (Luxury vs Business)
- Weekly trend lines for Occupancy, ADR, and RevPAR
- Booking platform revenue comparison
- Property-level performance table with cancellations and realization %

---

## 🛠️ Tech Stack

| Tool / Technology | Purpose |
|---|---|
| **Python** (Pandas, NumPy) | Data cleaning, transformation, and derived metric creation |
| **Power BI Desktop** | Data modeling, DAX measures, interactive dashboard design |
| **CSV Files** | Raw and dimensional data storage |
| **Star Schema** | Data modeling pattern for optimised Power BI performance |
| **DAX (Data Analysis Expressions)** | Calculated KPI measures within Power BI |

---

## 🔄 Data Pipeline (ETL Process)

```
Raw CSV Data
     │
     ▼
┌─────────────────────────────┐
│   Python (Pandas / NumPy)   │
│  • Handle missing values     │
│  • Remove duplicates         │
│  • Fix data types            │
│  • Standardise categories    │
│    (city, room types, etc.)  │
│  • Derive KPIs:              │
│    - Occupancy Rate          │
│    - ADR                     │
│    - RevPAR                  │
└─────────────────────────────┘
     │
     ▼
Clean / Transformed CSVs
     │
     ▼
┌─────────────────────────────┐
│        Power BI              │
│  • Star Schema Modeling      │
│  • DAX Calculated Measures   │
│  • Interactive Dashboard     │
└─────────────────────────────┘
```

---

## 📁 Data Sources

All data is stored as CSV files in the repository and serves as the primary input to the Power BI dashboard:

| File | Description |
|---|---|
| `dim_date.csv` | Date dimensions: `date`, `mmm yy`, `week no`, `day_type` (weekday/weekend) |
| `dim_hotels.csv` | Hotel property details (name, category, city) |
| `dim_rooms.csv` | Room type dimensions (room class, category) |
| `fact_aggregated_bookings.csv` | Pre-aggregated booking data for higher-level KPI analysis |
| `fact_bookings.csv` | Granular, transaction-level booking records |

### Data Model (Star Schema)

```
        dim_date
           │
dim_hotels ─── fact_bookings ─── dim_rooms
           │
  fact_aggregated_bookings
```

---

## 🚀 Quick Start

### Prerequisites

- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free download)
- Python 3.8+ with `pandas` and `numpy` (for data preprocessing, if re-running ETL)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/githubgitesh/Hospitality-

# 2. Navigate to the project folder
cd Hospitality-

# 3. (Optional) Install Python dependencies for ETL
pip install pandas numpy
```

### Run the Dashboard

1. Open `Dashboard Hospitality.pbix` in **Power BI Desktop**
2. The dashboard loads automatically, connecting to the local CSV files
3. Use slicers (date, hotel, room type, platform) to explore the data
4. To refresh with updated data, click **Home → Refresh** in Power BI Desktop

---

## 📖 Usage Guide

| Action | How To |
|---|---|
| Filter by date / hotel / room | Use the slicers on the left/top panel |
| Drill into a KPI | Click on any chart visual to cross-filter the dashboard |
| View weekly trends | Navigate to the trend analysis tab |
| Compare booking channels | Refer to the platform revenue breakdown visual |
| Refresh data | Update CSVs → Open `.pbix` → Click Refresh |

---

## ⚡ Challenges & Solutions

| Challenge | Solution |
|---|---|
| Poor data quality — missing values, duplicates | Applied Python (Pandas) cleaning pipeline before loading |
| Inconsistent categorical fields (city/room names) | Standardised using `.str.strip()`, `.str.lower()`, and value mapping |
| Complex DAX measures producing incorrect totals | Resolved through iterative testing and use of `CALCULATE` with proper filter context |
| Data from multiple booking platforms not unified | Normalised platform names and merged records via common keys |

---

## 🏗️ Skills Demonstrated

- ✅ End-to-end Data Analysis Lifecycle
- ✅ ETL using Python (Pandas, NumPy)
- ✅ Data Modeling — Star Schema (Fact & Dimension tables)
- ✅ DAX for KPI calculation in Power BI
- ✅ Business Analysis & Insight Generation
- ✅ Dashboard Design & Storytelling with Data
- ✅ Hospitality Domain KPIs (ADR, RevPAR, Occupancy Rate)

---

## 🚀 Roadmap

- [ ] Integrate live API / database connection for real-time data refresh
- [ ] Add predictive modeling for booking demand and revenue forecasting
- [ ] Implement Python-based anomaly detection for unusual booking patterns
- [ ] Build custom Power BI visuals for enhanced storytelling
- [ ] Expand property coverage and add multi-region support
- [ ] Improve documentation for data dictionary and DAX measure logic

---

## 👋 Contributing

Contributions are welcome! If you have suggestions for improvements, new features, or find any issues, feel free to open a pull request or raise an issue.

Top Contributors:
- [githubgitesh](https://github.com/githubgitesh)
- [yadnyeshkolte](https://github.com/yadnyeshkolte)

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 📜 Changelog

### v1.0.0 — 2026-04-17
- Initial project setup with full ETL pipeline and Power BI dashboard
- Included all core CSV data files (dim + fact tables)
- Implemented KPI measures: Revenue, Occupancy Rate, ADR, RevPAR
- Built interactive dashboard with property-level performance table and booking platform analysis
- Documented star schema data model and DAX measure logic
