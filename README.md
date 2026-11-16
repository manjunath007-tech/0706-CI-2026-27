# Zomato Restaurant Data Analysis (Skill Lab – CIE 1 Milestone 1)

## Overview
This repository holds my submission for **Skill Lab CIE-1 (Milestone 1)**. 

I selected a **Zomato Restaurants Dataset (`zomato_restaurants_data.csv`)** containing **550 restaurant records** across 8 Indian cities (`Bengaluru`, `Mangaluru`, `Mumbai`, `Hyderabad`, `Pune`, `Chennai`, `Delhi NCR`, and `Mysuru`). The goal of this work is to clean and transform the data using Pandas, fix missing values using **mean imputation**, and analyze how pricing, cuisine types, online ordering, and delivery speed affect customer ratings and monthly orders.

## Repository Contents
- **`Zomato_Restaurant_Analysis_CIE1.ipynb`** – Jupyter Notebook containing all Python and Pandas code, step-by-step comments, summary tables, and charts.
- **`zomato_restaurants_data.csv`** – The 550-row CSV dataset used in the notebook.
- **`README.md`** – Documentation explaining the dataset and steps completed.

## Step-by-Step Summary of Work Done

1. **Dataset Selection & Reading**
   - Imported `pandas`, `numpy`, `matplotlib.pyplot`, and `seaborn`.
   - Loaded `zomato_restaurants_data.csv` using `pd.read_csv()` and previewed the first 5 rows with `head()`.

2. **Data Understanding**
   - Checked the number of rows and columns (`550 rows × 15 columns`), column names, and data types using `info()` and `describe()`.
   - Explored the unique cities and cuisine categories present in the dataset.

3. **Data Transformation**
   - **Dropped unnecessary columns:** Removed `FSSAI_Batch_Code` and `Internal_Audit_Notes` since they were internal administrative fields.
   - **Changed data types:** Converted `Established_Year` to integer (`int64`) and created a binary numeric flag (`Online_Order_Flag`: `1` for Yes, `0` for No).
   - **Created new columns:**
     - `Restaurant_Age_Years`: Calculated how many years each restaurant has been operating (`2026 - Established_Year`).
     - `Cost_Per_Person`: Divided `Avg_Cost_For_Two` by 2.
     - `Price_Bracket`: Grouped restaurants into `Budget (<=500)`, `Mid-Range (501-1100)`, and `Premium (>1100)`.

4. **Handling Null Values (Mean Imputation)**
   - Checked missing value counts across all columns with `isnull().sum()`.
   - Imputed missing (`NaN`) values in `Avg_Cost_For_Two`, `Avg_Delivery_Time_Mins`, `Customer_Rating`, `Total_Votes`, and `Monthly_Orders` using each column's **mean** (`fillna(col_mean)`).
   - Verified that all columns had `0` missing values remaining after imputation.

5. **Insight Generation**
   - **City-wise Performance:** Compared restaurant counts, average dining cost, average rating, delivery times, and total monthly orders across cities.
   - **Cuisine-wise Trends:** Analyzed which cuisine types (`North Indian`, `South Indian`, `Biryani & Mughlai`, `Fast Food & Burgers`, etc.) receive the highest average monthly orders and ratings.
   - **Online Ordering Impact:** Found that restaurants with online ordering enabled (`Yes`) get higher average ratings and more monthly orders than offline-only outlets.

6. **Data Visualization**
   - **Vertical Bar Chart:** Total monthly orders across different cities.
   - **Horizontal Bar Chart:** Average monthly orders per restaurant across cuisine types.
   - **Box Plot:** Customer rating distribution comparing restaurants with and without online ordering.
   - **Scatter Plot:** Average delivery time vs. customer rating colored by price bracket.

## Steps to Run the Notebook
1. Download or clone this repository so that `Zomato_Restaurant_Analysis_CIE1.ipynb` and `zomato_restaurants_data.csv` are in the same directory.
2. Install the required Python libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```
3. Open `Zomato_Restaurant_Analysis_CIE1.ipynb` in **VS Code** or **Jupyter Notebook** and run the cells from top to bottom.
