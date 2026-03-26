# Uber NYC Rides Analysis (Jan–Jun 2015)

## Project Overview
This project analyzes Uber ride data in New York City from January to June 2015. The goal is to explore ride patterns, identify peak demand periods, and provide actionable insights for ride scheduling, resource allocation, and service optimization.

Using data analysis and visualization techniques, the project uncovers temporal trends in Uber trips and highlights high-demand periods across months and weekdays.

---

## Dataset
**Source:** Uber raw data (Jan–Jun 2015)  
**Kaggle Link:** [Uber Pickups in New York City](https://www.kaggle.com/datasets/fivethirtyeight/uber-pickups-in-new-york-city)  
**File:** `uber-raw-data-janjune-15.csv`  

**Columns include:**
- `Dispatching_base_num` – Uber dispatching base code  
- `Pickup_date` – Timestamp of ride pickup  
- `Affiliated_base_num` – Associated base number  
- `locationID` – Location identifier  

**Dataset Size:** ~6 months of ride data with hundreds of thousands of records

---

## Technologies and Libraries
- **Python 3.10+**  
- **Data Manipulation:** pandas, numpy  
- **Visualization:** matplotlib, seaborn, plotly.express  
- **OS & File Management:** os  

---

## Project Workflow
1. **Data Extraction & Cleaning**  
   - Load dataset and remove duplicates  
   - Handle missing values  
   - Correct data types for analysis  

2. **Feature Engineering**  
   - Extract month, weekday, day, hour, and minute from ride timestamps  

3. **Exploratory Data Analysis (EDA)**  
   - Month-wise analysis to identify peak months for rides  
   - Weekday analysis to observe trends across the week  

4. **Visualizations**  
   - Bar charts for monthly Uber trips  
   - Grouped bar charts for month vs weekday ride patterns  

5. **Key Insights**  
   - Fridays and Saturdays consistently have the highest ride volumes  
   - Weekdays (Monday–Wednesday) show lower ride volumes  
   - Clear weekday-weekend trends guide:  
     - Driver scheduling  
     - Resource allocation  
     - Targeted promotions  

---

## Visualizations
- **Monthly Uber Trips** – Shows the number of rides per month  
- **Uber Trips by Month and Weekday** – Highlights peak weekdays for rides  

*(Images are saved in the `/images` folder in the repository)*

---

## Usage Instructions
1. Clone or download the repository  
2. Place the dataset in the `/Datasets` folder  
3. Open the Jupyter Notebook or Python script to explore the analysis  
4. Visualizations and charts will be generated automatically  

---

## Future Improvements
- Add geospatial visualizations for NYC neighbourhoods  
- Explore hourly ride patterns for more granular insights  
- Build predictive models to forecast ride demand  

---

## Author
**OKPRO SUNDAY**  
Data Analyst  

- GitHub: [https://github.com/SundayOkpro](https://github.com/SundayOkpro)  
- LinkedIn: [https://www.linkedin.com/in/sunday-okpro-983072112/](https://www.linkedin.com/in/sunday-okpro-983072112/)
