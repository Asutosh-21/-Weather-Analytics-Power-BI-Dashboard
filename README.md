# 🌦️ Power BI Real Time  Weather Dashboard Project

A real-time, multi-city **Weather Dashboard** built with **Power BI** and **WeatherAPI**, this project showcases dynamic visualizations for current weather, forecasts, AQI indicators, sunrise/sunset times, and more. Ideal for portfolio display and real-world applications, it empowers users to build an auto-refreshing, API-integrated dashboard without complex backend setups.

---

## 📌 Summary

This project demonstrates how to build a fully dynamic weather analytics dashboard in Power BI using real-time JSON data from WeatherAPI. You’ll learn how to call APIs, clean and transform data, create powerful visuals, and deploy the dashboard with automatic updates.

---



---

## 🧠 Key Insights

- 🌍 **APIs democratize real-time data** — No expensive infrastructure needed.
- 🛠️ **Power BI + Web Data** = Fast and efficient dashboard development.
- 📈 **Data cleaning and normalization** enable multi-city scalability.
- 🎯 **User experience** enhanced with clean UI, slicers, icons, formatting.
- 🔄 **Data model relationships** enable smooth, dynamic filtering.
- 📅 **Time formatting & sorting** keeps trend visuals accurate and intuitive.
- 🚀 **Scheduled refresh** keeps dashboards live and actionable.

---

## 🛠️ Prerequisites

- ✅ WeatherAPI.com account (Free or Paid)
- ✅ Power BI Desktop installed
- ✅ Basic Power BI knowledge

---

## 🔑 Step 1: Get Your WeatherAPI Key

- Go to [https://www.weatherapi.com](https://www.weatherapi.com)
- Sign up and copy your **API Key**

---

## 🌐 Step 2: Build the API URL

Replace `YOUR_API_KEY` and `CITY_NAME` in the template:  [(https://api.weatherapi.com/v1/current.json?key=YOUR_API_KEY&q=CITY_NAME)](https://www.weatherapi.com/)


---

## 🧠 Step 3: Connect Power BI to WeatherAPI

1. Open Power BI Desktop
2. Click **Get Data → Web**
3. Paste the API URL
4. Load into Power Query Editor
5. Expand:
   - `current`
   - `condition`
   - `air_quality`
6. Rename columns clearly
7. Click **Close & Apply**

---

## 🧹 Step 4: Transform the Data

- Create separate tables:
  - `Current_Weather`
  - `Hourly_Forecast`
  - `Daily_Forecast`
- Clean nulls, drop unnecessary fields
- Build relationships among tables

---

## 📊 Step 5: Build Your Dashboard

Add visuals such as:
- ✅ Cards: temperature, humidity, pressure
- ✅ Gauges: wind speed, AQI
- ✅ Bar/Line charts: hourly & daily forecasts
- ✅ Map visual for city locations

Apply filters/slicers for city and time range.

---

## 🎨 Step 6: Styling & Interactivity

- Use a **Dark Theme** for a modern look
- Insert weather icons via URL or local files
- Apply **conditional formatting** to KPIs
- Enable interactive slicers for city/date

---

## 🌫️ Step 7: Add AQI Indicators with DAX

Use these **reusable templates**:

### 🟢 AQI Color Indicator

```DAX
AQI Color =
VAR AQI = ROUND(SELECTEDVALUE('Current'[current.air_quality.COLUMN_NAME]), 0)
RETURN SWITCH(TRUE(),
  AQI <= 50, "#43d946",
  AQI <= 100, "#fff570",
  AQI <= 150, "#ff9800",
  AQI <= 200, "#d99343",
  AQI <= 300, "#ff5b0f",
  "#d95243"
)
AQI Suggestion =
VAR AQI = ROUND(SELECTEDVALUE('Current'[current.air_quality.COLUMN_NAME]), 0)
RETURN SWITCH(TRUE(),
  AQI <= 50, "Air is clean and healthy",
  AQI <= 100, "Acceptable air quality, stay active",
  AQI <= 150, "Sensitive groups should reduce outdoor time",
  AQI <= 200, "Limit prolonged outdoor exertion",
  AQI <= 300, "Avoid outdoor activity if possible",
  "Stay indoors, wear a mask if outside"
)


💬 Final Thoughts
This Power BI project is perfect for:

📈 Enhancing your analytics portfolio

🎓 Practicing real-world BI solutions

🧠 Understanding API + BI integration

🚀 Deploying dashboards with live updates

