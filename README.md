🏋 **Power BI Fitness Center Analytics Dashboard**

📌 **Project Overview**

This project is a **Power BI analytics dashboard** built for a **fitness center** to **centralize operational, financial, and membership insights**. The primary objective was to replace multiple Excel-based reports with a single interactive dashboard that supports leadership in monthly business review and decision-making.

🎯 **Client Requirements**

The client requested a dashboard that:

🔹 Displays active vs expired members based on membership plan (Gold, Silver, Bronze).

🔹 Shows trainer insights and gender distribution.

🔹 Tracks revenue, expenses, and profit month-wise.

🔹 Includes payment preference analysis.

🔹 Contains simple navigation between pages.

🔹 Enables future attendance monitoring once data becomes available.

🔧 **Solution Delivered**

A 3-page interactive Power BI report:

1️⃣ **Home Page**

🔹 Navigation buttons to **Dashboard and Attendance**

2️⃣ **Dashboard Page**

🔹 Date range slicer for dynamic filtering

🔹 Membership cards with donut charts **(Gold | Silver | Bronze → Active vs Expired).**

🔹 Member & trainer gender distribution

🔹 Branch insights

🔹 Payment preference donut chart

📍 Finance view:

🔹 Monthly Revenue

🔹 Monthly Expenses

🔹 Monthly Profit

🔹 Expense type slicer

🔹 Cards for Revenue, Profit and Expenses

3️⃣ **Attendance Page**

🔹Structure designed for future expansion (awaiting client data)

🧠 **Technical Implementation**

🔹 **Modeling & Relationships**

✔ Connected Users, Payments, Expenses, and Calendar tables

✔ Built a consolidated finance table for month-based trend analysis

🔹 **Key DAX Measures (Highlights)**

✔ Bronze_active_members = CALCULATE(COUNTROWS(Users), Users[Membership] = "Bronze", Users[Status] = "Active")

✔ Silver_inactive_members = CALCULATE(COUNTROWS(Users), Users[Membership] = "Silver", Users[Status] = "Expired")

✔ Profit = SUM(Payments[Amount])

✔ Expenses = SUM(Expenses[Amount])

✔ Revenue = [Profit] - [Expenses]

✔ T_Male = COALESCE(CALCULATE(COUNTROWS(Users), Users[Gender] = "Male"), 0)

🔹 **Personalized Greeting DAX**
Greeting =
VAR H = HOUR(NOW())
RETURN
SWITCH(TRUE(),
    H >= 5 && H < 12, "🌞 Good Morning",
    H >= 12 && H < 16, "🌤️ Good Afternoon",
    H >= 16 && H < 20, "🌇 Good Evening",
    "🌙 Good Night"
)

📌 **Business Impact**

The dashboard enabled the fitness center to:

🔹 Monitor membership renewal instantly

🔹 Identify revenue fluctuations and track expenses

🔹 Improve trainer allocation based on gender & membership distribution

🔹 Reduce manual report preparation effort

🔹 Support financial and operational decision-making in a single view

🛠 **Tools & Skills Used**

✔ BI Tool	Power BI

✔ Language	DAX

✔ Modeling	Star schema, relationship management

✔ Visuals	KPI cards, donut charts, bar charts, area chart

✔ UX	Custom navigation buttons, time-based greeting

🚀 **Future Enhancements**

✔ Activate attendance analytics once the dataset is available

✔ Add member retention predictors & expiry reminders

✔ Integrate WhatsApp API for automated renewal alerts
