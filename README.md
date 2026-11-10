# Call Center Sales Dashboard - Task 4

## 📌 Project Overview
This repository contains the deliverables for Task 4: Dashboard Design. The objective was to create an interactive dashboard for business stakeholders using a Sales dataset. 

**Tools Used:** Power BI (Free Desktop Version), CSV Data.

## 📂 Dataset Information
The dataset (`Product_Sales.csv`) contains simulated call center data with the following columns:
- `AgentID` / `Agent_Name`: Identity of the sales agent.
- `CallID` / `CustomerID`: Unique identifiers.
- `PickedUp`: Binary (1 = Call answered, 0 = Missed).
- `Duration`: Length of call in seconds.
- `ProductSold`: Binary (1 = Sale made, 0 = No sale).

*Note: The original dataset lacked a Date column. A synthetic `Call_Date` column was generated via Power Query to fulfill the time-series analysis requirement.*

## 🛠️ Steps to Reproduce
1. **Data Cleaning (Power Query):**
   - Removed rows with negative `Duration`.
   - Changed data types (Boolean for `PickedUp` & `ProductSold`).
   - Added a custom synthetic `Call_Date` column for trend analysis.
2. **DAX Measures Created:**
   - `Total Calls = COUNT(Product_Sales[CallID])`
   - `Total Picked Up = CALCULATE(COUNT(Product_Sales[CallID]), Product_Sales[PickedUp] = 1)`
   - `Total Sales = CALCULATE(COUNT(Product_Sales[CallID]), Product_Sales[ProductSold] = 1)`
   - `Conversion Rate = DIVIDE([Total Sales], [Total Picked Up], 0)`
3. **Visualizations Built:**
   - **Cards:** Total Calls, Total Sales, Conversion Rate.
   - **Line Chart:** Call Volume and Sales Trends over `Call_Date`.
   - **Bar Chart:** Sales by Agent.
   - **Donut Chart:** Call Pickup vs. Missed Calls.
   - **Slicer:** Filter by Agent Name.

## 📊 Dashboard Screenshots
*(Add a screenshot of your Power BI dashboard here after you build it)*
<!-- ![Dashboard](screenshot.png) -->

## 💡 Key Insights derived
- The overall conversion rate is around **45%** (Based on simulated data).
- Missed calls account for a significant portion of the dataset, indicating a potential need for better staffing or automated callback systems.
- Certain agents consistently outperform others in both call pickup rate and sales conversion.

## 🧠 Interview Questions Addressed
Please refer to the `Interview_QA.md` file in this repository for detailed answers to the interview questions provided in the task guidelines.

## 🚀 How to View
1. Clone the repository.
2. Open the `.pbix` file (if included) using Power BI Desktop.
3. If you do not have Power BI, refer to the step-by-step guide in `Dashboard_Guide.md`.
