# 🚚 Logistics Performance Dashboard – Power BI

 📊 Project Overview
The **Logistics Performance Dashboard** is a Power BI analytics solution designed to monitor and optimize logistics operations across **orders, hubs, drivers, and vehicles**.
This dashboard provides operational visibility to help logistics managers track performance, identify bottlenecks, and make data-driven decisions.
The project demonstrates how **data analytics and visualization can improve operational efficiency in the logistics industry.**

# 🎯 Business Problem
Logistics companies handle thousands of deliveries daily. Without proper analytics, it becomes difficult to:
- Monitor delivery performance
- Track driver productivity
- Manage hub capacity
- Optimize fleet utilization
- Identify operational bottlenecks
This project builds a **centralized analytics dashboard** that enables stakeholders to monitor logistics operations efficiently.

# 🎯 Business Objectives
The dashboard answers the following business questions:
- How many orders are processed monthly?
- What is the **on-time delivery rate**?
- Which hubs are **overloaded or underutilized**?
- Which drivers are responsible for **delivery delays**?
- Which vehicle models handle **most deliveries**?
- Are **older vehicles causing more breakdowns**?

# 📊 Dashboard Architecture
The Power BI solution consists of **four analytical dashboards**:
1️⃣ **Logistics Overview Dashboard**  
2️⃣ **Hub Performance Dashboard**  
3️⃣ **Driver Analytics Dashboard**  
4️⃣ **Vehicle Performance Dashboard**

# 📈 Dashboard 1 – Logistics Overview
This dashboard provides **high-level KPIs for logistics operations.**
 Key Metrics
- 📦 **Total Orders**
- 📊 **Month-over-Month Growth**
- ⏱ **On-Time Delivery Rate**
- ⭐ **Customer Satisfaction Score (CSAT)**
- 🚚 **Average Delivery Time**
Business Value
Helps management monitor overall logistics performance and detect operational inefficiencies.

# 🏢 Hub Analytics
Key Insights
- Total number of hubs
- Orders processed by each hub
- Hub capacity vs orders handled
- Hub performance ranking
Business Value
- Identify **overloaded hubs**
- Detect **underutilized hubs**
- Improve **hub resource allocation**

# 🚛 Driver Analytics
 Key Insights
- Total number of drivers
- Driver experience vs customer rating
- Drivers causing the most delays
- Individual driver performance summary
- Monthly delivery trends
 Business Value
- Monitor driver productivity
- Identify training requirements
- Improve delivery efficiency

# 🚚 Vehicle Analytics
 Key Insights
- Total fleet size
- Active vs inactive vehicles
- Orders handled by vehicle model
- Vehicle age vs breakdown frequency
- Vehicle performance comparison
 Business Value
- Optimize fleet utilization
- Identify vehicles needing maintenance
- Reduce operational disruptions

# 🧠 Key Business Insights

Using this dashboard, logistics managers can:
- Improve **on-time delivery performance**
- Detect **hub capacity issues**
- Monitor **driver productivity**
- Optimize **fleet usage**
- Reduce **vehicle breakdowns**
- Enhance **customer satisfaction**

# 🛠 Tools & Technologies

- **Power BI**
- **Power Query**
- **DAX**
- **Data Modeling**
- **Data Visualization**

---

# 📂 Project Structure

# Project Architecture
Data Sources
      │
      ▼
Raw Logistics Data
(Orders, Drivers, Vehicles, Hubs)
      │
      ▼
Power Query (Data Cleaning & Transformation)
      │
      ▼
Data Modeling
(Relationships between fact & dimension tables)
      │
      ▼
DAX Calculations
(KPIs & Measures)
      │
      ▼
Power BI Dashboards
(Interactive Visualizations)

#  Data Model Explanation
The project follows a **Star Schema data model** to improve performance and simplify reporting.
# Fact Table
# Fact_Orders
Contains transactional logistics data.
Important columns:
- Order ID
- Driver ID
- Vehicle ID
- Hub ID
- Delivery Time
- Delivery Status
- Customer Rating

# Dimension Tables
# Dim_Drivers
Contains driver details:
- Driver ID
- Driver Name
- Experience
- Rating
- Hire Date

# Dim_Vehicles
Contains vehicle details:
- Vehicle ID
- Vehicle Model
- Vehicle Type
- Vehicle Age
- Breakdown Count

# Dim_Hubs
Contains logistics hub information:
- Hub ID
- Hub Location
- Hub Capacity

  # Dim_Date
Used for time-based analysis.
Columns include:
- Date
- Month
- Year
- Quarter

#  Table Relationships
Fact_Orders[DriverID] → Dim_Drivers[DriverID]
Fact_Orders[VehicleID] → Dim_Vehicles[VehicleID]
Fact_Orders[HubID] → Dim_Hubs[HubID]
Fact_Orders[OrderDate] → Dim_Date[Date]

#  DAX Measures Used in the Dashboard
Below are the key DAX measures used to calculate the business KPIs in the Power BI dashboard.
# DAX
-- Total Orders
Total Orders =
COUNT(Fact_Orders[OrderID])

-- Previous Month Orders
Previous Month Orders =
CALCULATE(
    [Total Orders],
    DATEADD(Dim_Date[Date], -1, MONTH)
)

-- Month over Month Growth %
MoM Growth % =
DIVIDE(
    [Total Orders] - [Previous Month Orders],
    [Previous Month Orders]
)

-- On-Time Delivery Rate
On-Time Delivery Rate =
DIVIDE(
    CALCULATE(
        COUNT(Fact_Orders[OrderID]),
        Fact_Orders[DeliveryStatus] = "On Time"
    ),
    [Total Orders]
)

-- Average Delivery Time
Average Delivery Time =
AVERAGE(Fact_Orders[DeliveryTime])

-- Customer Satisfaction Score
CSAT Score =
AVERAGE(Fact_Orders[CustomerRating])

# 📊 KPI Definitions

Below are the key performance indicators used in the dashboard.

**Total Orders**  
Total number of orders processed in the selected time period.

**Month-over-Month Growth (MoM Growth)**  
Percentage change in orders compared to the previous month.

**On-Time Delivery Rate**  
Percentage of orders delivered within the expected delivery time.

**Average Delivery Time**  
Average time taken to complete deliveries.

**Customer Satisfaction Score (CSAT)**  
Average rating given by customers after delivery completion.

---

#  Key Insights from the Dashboard
The analysis of logistics data revealed several operational insights.
**1. Delivery Performance**
- The on-time delivery rate helps identify operational efficiency.
- Lower rates indicate possible delays in hubs, drivers, or vehicle availability.
**2. Hub Capacity Utilization**
- Some hubs process significantly more orders compared to their capacity.
- This may lead to operational bottlenecks and delivery delays.
**3. Driver Performance**
- Drivers with higher experience tend to receive better customer ratings.
- Some drivers contribute to a higher number of delayed deliveries.
**4. Fleet Utilization**
- Certain vehicle models handle a higher share of deliveries.
- Older vehicles tend to have a higher number of breakdowns.
**5. Demand Trends**
- Monthly order trends show fluctuations in delivery demand.
- These trends can help logistics companies plan workforce and fleet allocation.

#  Business Recommendations
Based on the insights derived from the dashboard:
**Improve Hub Capacity Planning**
- Balance order distribution across hubs to avoid overload.
**Driver Performance Monitoring**
- Provide training to drivers contributing to delays.
**Fleet Maintenance Strategy**
- Replace or maintain vehicles with frequent breakdowns.
**Demand Forecasting**
- Use historical trends to forecast delivery demand.
**Operational Efficiency**
- Monitor delivery KPIs regularly to improve service reliability.

#  Skills Demonstrated
This project demonstrates the following skills:
- Data Cleaning & Transformation
- Data Modeling (Star Schema)
- DAX Calculations
- KPI Development
- Business Intelligence Reporting
- Dashboard Design
- Analytical Storytelling

#  Key Learnings from This Project
During the development of this project, several important data analytics concepts were applied and strengthened:
- Designing **business-focused KPIs** for logistics operations.
- Building a **star schema data model** for efficient reporting.
- Writing **DAX measures** to calculate business metrics.
- Transforming raw operational data using **Power Query**.
- Creating **interactive dashboards** for business users.
- Translating raw data into **actionable business insights**.

This project helped strengthen both **technical analytics skills and business problem-solving abilities**.

#  Project Files
The repository includes the following files:
- **GlobalLink Logistics Project.pbix** – Power BI dashboard file  
- **Data Files** - Contains all the files 

# 👨‍💻 Author
**Anand Bharadwaj**

Aspiring Data Analyst  
Skilled in **Power BI, SQL, Python, and Data Visualization**

🔗 LinkedIn: * https://www.linkedin.com/in/medurivsanandbharadwaj *

---

⭐ If you found this project useful, please consider **starring the repository**.
