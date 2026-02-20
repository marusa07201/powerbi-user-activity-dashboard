# 📊 User Activity & Revenue Dashboard (Power BI)

## 📌 Project Overview
This project focuses on analyzing user behavior, conversion rate and revenue using event-based data.

The dashboard provides insights into:
- User activity
- Order volume
- Revenue performance
- Conversion rate
- ARPU (Average Revenue Per User)

The goal is to support data-driven product and marketing decisions.

---

## 🗂 Dataset Description

The analysis is based on three datasets:

**users.csv**
- user_id
- reg_date
- country
- source
- device

**events.csv**
- event_time
- user_id
- event_name
- platform
- session_id

**orders.csv**
- order_id
- user_id
- order_date
- revenue
- currency
- product_type

---

## 🧹 Data Preparation

Data cleaning and transformation were performed in Power Query:
- Removed duplicate user_id values in users table
- Handled missing values in country column ("Other countries")
- Filtered out blank user_id values in events and orders tables
- Created event_date column from event_time
- Created Date dimension table

---

## 🧩 Data Model

A star schema data model was implemented:

- users → dimension table  
- events → fact table  
- orders → fact table  
- Date → dimension table  

Relationships:
- users[user_id] → events[user_id]
- users[user_id] → orders[user_id]
- Date[Date] → events[event_date]
- Date[Date] → orders[order_date]

---

## 📐 Key Metrics (DAX)

- Total Users
- Active Users
- Orders Count
- Total Revenue (Gross)
- Total Revenue (Net)
- ARPU
- Conversion Rate

---

## 📈 Dashboard Features

**KPI Cards**
- Users
- Active Users
- Orders
- Revenue Gross
- Revenue Net
- ARPU
- Conversion Rate

**Visualizations**
- Users by Date
- Orders by Date
- Revenue Gross vs Net by Date
- Revenue Net by Week
- Revenue by Country

**Filters**
- Date
- Country
- Source
- Device
- Time to Convert

---

## 💡 Insights & Growth Hypotheses

Possible growth opportunities:
- Users from specific acquisition sources may convert better than others
- Some countries may generate higher ARPU
- Mobile vs Desktop users may show different conversion patterns

These hypotheses can be tested to improve marketing performance and product strategy.

---

## 🛠 Tools Used
- Power BI
- DAX
- Power Query (M)

---

## 📎 Files
Dashboard file is available in:
dashboard/User_Activity_And_Revenue.pbix
