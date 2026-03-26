# Uber NYC Rides Analysis (Jan–Jun 2015)

## Project Overview
This project analyzes Uber ride data in New York City from January to June 2015. The goal is to explore ride patterns, identify peak demand periods, and provide actionable insights for ride scheduling, resource allocation, and service optimization.

Using Python and popular analytics libraries, this project performs data cleaning, feature engineering, exploratory data analysis (EDA), and visualization to uncover temporal trends in Uber trips.

---

# Dataset
**Source:** Uber raw data (Jan–Jun 2015)  
**File:** `uber-raw-data-janjune-15.csv`  

**Columns include:**
- `Dispatching_base_num
- Pickup_date
- Affiliated_base_num
- locationID


**Dataset Size:** ~6 months of ride data with hundreds of thousands of records

---

# Technologies and Libraries
- **Python 3.10+**
- **Data Manipulation:** pandas, numpy
- **Visualization:** matplotlib, seaborn, plotly.express
- **OS & File Management:** os

---

## Project Workflow

# 1️⃣ Data Extraction
import pandas as pd
import os

# Verify dataset
os.listdir(r"C:\Users\sunda\Downloads\Uber\Datasets")

#2️⃣ Data Cleaning
Remove duplicates
uber_15.drop_duplicates(inplace=True)

Check for missing values
print(uber_15.isnull().sum())

Convert Pickup_date to datetime
uber_15['Pickup_date'] = pd.to_datetime(uber_15['Pickup_date'])

#3️⃣ Feature Engineering
uber_15['month'] = uber_15['Pickup_date'].dt.month_name()
uber_15['weekday'] = uber_15['Pickup_date'].dt.day_name()
uber_15['day'] = uber_15['Pickup_date'].dt.day
uber_15['hour'] = uber_15['Pickup_date'].dt.hour
uber_15['minute'] = uber_15['Pickup_date'].dt.minute


#4️⃣ Month-wise Analysis


month_order = ["January","February","March","April","May","June"]
month_counts = uber_15['month'].value_counts().reindex(month_order)

plt.figure(figsize=(12,6))
month_counts.plot(kind='bar', color='skyblue', edgecolor='black')
plt.title("Number of Uber Trips per Month", fontsize=14, fontweight='bold')
plt.xlabel("Month", fontsize=12)
plt.ylabel("Number of Trips", fontsize=12)
plt.xticks(rotation=45)
plt.grid(axis='y', linestyle='--', alpha=0.7)
plt.tight_layout()
plt.show()


#5️⃣ Crosstab Analysis (Month vs Weekday)
weekday_order = ["Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"]

pivot = pd.crosstab(index=uber_15['month'], columns=uber_15['weekday'])
pivot = pivot.reindex(index=month_order, columns=weekday_order)
pivot.head()

#6️⃣ Grouped Bar Chart (Plotly Express)
import plotly.express as px
fig = px.bar(
    pivot,
    x=pivot.index,
    y=pivot.columns,
    barmode='group',
    title="Uber Trips by Month and Weekday"
)
fig.update_layout(
    xaxis_title="Month",
    yaxis_title="Number of Trips",
    legend_title="Weekday",
    xaxis_tickangle=-45,
    template="plotly_white")

fig.show()

# Save interactive chart as static image for README
fig.write_image("./images/month_weekday_trips.png")

##7️⃣ Key Insights
Fridays and Saturdays consistently have the highest ride volumes.
Weekdays (Monday–Wednesday) show lower ride volumes.
There is a clear weekday-weekend trend that can guide:
Driver scheduling
Resource allocation
Targeted promotions
Visualizations
Monthly Uber Trips





##OKPRO SUNDAY
Data Analyst

GitHub: https://github.com/SundayOkpro
LinkedIn: https://www.linkedin.com/in/sunday-okpro-983072112/
