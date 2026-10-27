# 🏨 Hotel Bookings Analytics & Cancellation Prediction Pipeline

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status: Active](https://img.shields.io/badge/Status-Active%20Development-brightgreen.svg)]()
[![Python](https://img.shields.io/badge/Python-Data%20Engineering%20%26%20EDA-blue.svg)]()

## 📌 Overview
`hotel_bookings-Project` is an open-source data engineering, exploratory data analysis (EDA), and predictive modeling framework designed to analyze hospitality demand, customer booking trends, and cancellation patterns.

While raw hospitality datasets are widely available, this repository provides a standardized, reproducible end-to-end pipeline—from messy transactional records to cleaned datasets, visual telemetry, and interactive BI dashboards.

## 📊 Core Empirical Findings & Benchmark Insights
Through programmatic preprocessing and statistical exploration across transactional booking records, the pipeline surfaces critical revenue-management benchmarks:
- **Cancellation Risk Baseline:** Identifies an overall **~37% cancellation rate**, isolating high-risk lead times and deposit structures.
- **Seasonal Peak Modeling:** Captures seasonal demand surges, establishing **August** as the highest-volume occupancy window requiring dynamic pricing adjustments.
- **Distribution Channel Attribution:** Demonstrates that **Online Travel Agents (Online TA)** drive the primary share of booking volume, alongside higher sensitivity to last-minute cancellations.

## 📂 Repository Architecture
All core analytical workflows, visual exports, and presentation artifacts are organized inside the [`/hotel_booking`](./hotel_booking) directory:

```text
├── hotel_booking/
│   ├── eda_visualizations_v2/       # High-resolution statistical plots & visual telemetry
│   ├── slides/                      # Executive presentation decks & analytical summaries
│   ├── Hotel_Booking_Analysis.ipynb # Core Python data cleaning, imputation & EDA pipeline
│   └── README.md                    # Module-level notes and dataset specifications
├── LICENSE                          # MIT Open Source License
└── README.md                        # Root architecture documentation and roadmap
