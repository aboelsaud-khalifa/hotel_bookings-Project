# hotel_bookings-Project-ManusAI (Version 2)

## Smart Decisions with Hotel Booking Analytics

This project analyzes a real-world hotel booking dataset to uncover meaningful insights, perform comprehensive data cleaning, and provide actionable business recommendations. The final deliverable includes a cleaned dataset, a detailed Jupyter Notebook documenting the process, and an interactive Excel dashboard.

### Deliverables

1.  **Jupyter Notebook:** `Hotel_Booking_Analysis.ipynb` (Full cleaning and EDA process).
2.  **Cleaned Data:** `hotel_bookings_Cleaned_v2.csv` (The final, processed dataset from `hotel_bookings(2).csv`).
3.  **Excel Dashboard:** `hotel_bookings_Dashboard_v2.xlsx` (Contains the cleaned data ready for PivotTables and Slicers).
4.  **Documentation:** `README_v2.md` (This file).
5.  **Presentation Slides:** HTML files located in the `hotel_booking_presentation_v2` directory (for a 15-minute live presentation).

### How to Run the Analysis

The entire data cleaning and EDA process is contained within the `Hotel_Booking_Analysis.ipynb` Jupyter Notebook.

1.  **Prerequisites:** Ensure you have Python 3.x installed.
2.  **Setup Environment:**
    ```bash
    # Create and activate a virtual environment
    python3 -m venv venv
    source venv/bin/activate

    # Install required libraries
    pip install pandas numpy matplotlib seaborn jupyter openpyxl
    ```
3.  **Launch Jupyter:**
    ```bash
    jupyter notebook
    ```
4.  **Execute:** Open `Hotel_Booking_Analysis.ipynb` and run all cells sequentially. This will:
    *   Load the raw data (`hotel_bookings(2).csv`).
    *   Perform all data cleaning steps (handling missing values, correcting types, removing invalid records).
    *   Generate key visualizations, saving them to the `eda_visualizations_v2` directory.
    *   Export the final cleaned dataset to `hotel_bookings_Cleaned_v2.csv`.

### Key Findings (Summary of EDA)

The analysis of **87,230 valid bookings** revealed three critical insights:

| Finding | Detail | Business Implication |
| :--- | :--- | :--- |
| **Lower Overall Cancellation Rate** | The overall cancellation rate is **27.52%**, which is significantly lower than the previous dataset (37.08%). City Hotels have a higher rate compared to Resort Hotels. | The lower cancellation rate indicates improved booking quality. However, City Hotels still require targeted strategies to further reduce cancellations. |
| **Strong Seasonality** | Booking volume peaks consistently in the summer months (July/August), with a secondary peak in the fall. | Dynamic pricing and staffing models must be aligned with these predictable seasonal fluctuations. |
| **Price Sensitivity and Market Concentration** | Canceled bookings show a slightly lower Average Daily Rate (ADR) than non-canceled bookings. The top origin country is **Portugal (PRT)**, indicating strong domestic market concentration. | Price is a factor in cancellations. Marketing efforts should focus on strengthening the domestic market and key international segments. |

### Dataset Comparison

| Metric | Original Dataset | New Dataset (v2) |
| :--- | :--- | :--- |
| **Total Bookings** | 119,210 | 87,230 |
| **Overall Cancellation Rate** | 37.08% | 27.52% |
| **City Hotel Bookings** | 79,163 | 53,274 |
| **Resort Hotel Bookings** | 40,047 | 33,956 |

### Dashboard Guide (`hotel_bookings_Dashboard_v2.xlsx`)

The Excel file contains the final cleaned dataset in the **'Data'** sheet. To build the fully interactive dashboard:

1.  **Open** `hotel_bookings_Dashboard_v2.xlsx` in Microsoft Excel.
2.  **Insert PivotTable:** Select the entire 'Data' sheet, go to `Insert` -> `PivotTable`. Place the PivotTable on a new sheet named **'Dashboard'**.
3.  **Create Key PivotTables:**
    *   **Cancellation Rate by Hotel:** Rows: `hotel`, Columns: `is_canceled`, Values: Count of `is_canceled`.
    *   **Bookings by Month:** Rows: `arrival_date_month`, Values: Count of `hotel`.
    *   **ADR by Customer Type:** Rows: `customer_type`, Values: Average of `adr`.
4.  **Insert Charts:** Create a PivotChart for each PivotTable (e.g., a Column Chart for Cancellation Rate).
5.  **Add Interactivity (Slicers):** Select any PivotTable, go to `Analyze` -> `Insert Slicer`. Add slicers for key dimensions like `hotel`, `country`, `market_segment`, and `deposit_type`. Connect all PivotTables to these slicers.

### Presentation Slides

The presentation slides (HTML files in `hotel_booking_presentation_v2`) emphasize the problem, the solution process, and the key findings, with a focus on practical recommendations for a 15-minute live presentation.

### Data Cleaning Process

The data cleaning process addressed the following issues:

1.  **Missing Header Row:** The CSV file did not include a header row, requiring external research to identify the 32 column names.
2.  **Missing Values:** Imputed missing values strategically:
    *   `country`: Filled with "Unknown"
    *   `agent` and `company`: Filled with 0 (representing no agent/company)
    *   `children`: Filled with 0
    *   `adr`: Filled with the median value
3.  **Invalid Records:** Removed bookings with zero guests (adults, children, and babies all equal to zero).
4.  **Data Type Conversion:** Converted all numeric columns to appropriate types (int or float).
5.  **Feature Engineering:** Created a unified `arrival_date` column for easier time-series analysis.

### Key Recommendations

Based on the EDA findings, the following three strategic actions are recommended:

1.  **Optimize Pricing Strategy:** Implement dynamic pricing based on seasonal trends, maximizing ADR during peak months (July/August) and offering incentives during low seasons.
2.  **Strengthen Domestic Market:** Focus marketing efforts on the top 5 origin countries, particularly Portugal, to increase repeat guest rates and reduce reliance on third-party distribution channels.
3.  **Reduce City Hotel Cancellations:** Implement stricter deposit policies for City Hotel bookings, particularly during high-demand periods, to reduce the cancellation rate.
