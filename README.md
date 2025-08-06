## 📘 Project Summary: Food Waste Forecasting Using AI

### 1️⃣ Problem Statement

Food waste is a critical issue — millions go hungry daily, while edible food is discarded due to over-preparation and poor planning.  
In schools, especially canteens, food items (like fast food) are often made in bulk without knowing exact demand.

🔍 Our goal is to make an AI-based model that predicts food waste and suggests the ideal quantity to prepare, reducing waste and saving costs. 
This will not only help the canteen owner but also make everyone aware about the issue so that they can help more by trying to reduce food waste as much as they can. 

---

### 2️⃣ Users / Stakeholders

- 🍽️ **Canteen Owners & Food Vendors**
- 🏫 **School Administration**
- 📊 **Researchers & Data Scientists**
- 🌱 **Sustainability-focused NGOs**
- 📦 **Food Redistribution Programs**

---

### 3️⃣ Objectives

- Analyze historical canteen food data  
- Forecast likely waste based on trends  
- Recommend optimal quantities for preparation  
- Minimize food waste in school environments  
- Encourage responsible consumption

---

### 4️⃣ AI Techniques Used

- 🔢 **Linear Regression** to predict sold quantity  
- 🧩 **Rolling Averages** and rule-based logic to recommend preparation quantity

---

### 🧠 Recommendation Logic

Once sold quantity is predicted using machine learning, we calculate the **recommended food quantity** to prepare:

```python
df['Recommended_Qty'] = (df['Quantity_Sold'] + buffer).clip(lower=0).round()
```

Or, in absence of past sold info:
```python
df['Recommended_Qty'] = (df['Predicted_Sold'] + buffer).clip(lower=0).round()

```

The buffer ensures that sudden demand spikes don’t result in shortages. We cap all values to avoid negative recommendations.

---

### 5️⃣ Data Used

- 📅 Date
- 🍔 Food Item
- 🧾 Quantity Prepared
- ✅ Quantity Sold
- ♻️ Quantity Wasted (if available)
- 📍 Day of the Week / Special Events (derived)

---

### 6️⃣ Proposed Solution

- Predict how much quantity will be sold (using AI)
- Estimate expected waste if sold data isn’t available
- Recommend food quantity with minimal waste and max efficiency
- Output user-friendly, readable results for canteen staff

---

### 7️⃣ Sustainable Development Goals (SDGs)

- **SDG 2** – *Zero Hunger:* By reducing waste, more food can be redirected or used efficiently
- **SDG 12** – *Responsible Consumption and Production:* Promotes mindful preparation and consumption practices

---

### 8️⃣ Future Scope

- 📱 Mobile app for real-time use
- 📈 Live dashboards for canteen staff
- 📡 IoT integration for smart kitchen systems
- 🧾 Auto-reports for school admins
- ♻️ NGO/donation linking for unused food


## 👥 Team & Roles

This project was developed by a team of Class 12 AI students as part of a school initiative. Each member contributed to specific areas of the project:

- **Itikaa Rana (Team Lead and ML Developer)**  
  → Project planning, model logic design, dataset structuring, training/testing, prediction pipeline, visualizations, README creation

- **Anant Sharma (Data Analyst)**  
  → Data collection, cleaning, standardization logic, preprocessing pipeline, exploratory analysis

- **Tanisha Chaudhary (Video Creator & Project Presenter)**  
  → Explained the project idea, working, and real-life impact in video form clearly and confidently

- **Aahna Gautam (Testing & Output Visualizer)**  
  → Output formatting, graph development, user-friendly CSV display

- **Saksham Piyush Patil (Documentation & Presentation)**  
  → Final report drafting, presentation slides, file explanations

> 🔄 All members participated in brainstorming, idea refinement, peer reviews, and testing.

---

## 🧠 Project Phases Explained

This project is divided into **three phases**, solving different layers of the food waste problem using AI and analytics.

---

### 🟣 Phase 0: Data Analysis and Insight Extraction

**🎯 Objective**  
To understand item-level trends, sale frequency, and waste patterns before applying ML. This helps canteen staff gain insights even before predictions.

**🛠️ How it works**
- Input CSV file with all columns (`Prepared`, `Sold`, `Waste`)
- Generates:
  - 📊 Waste frequency per item
  - 📈 Item-wise sales trends
  - 🧾 Most & least wasted items
  - 📍 Analysis by day of the week
- Outputs graphs & summary tables

✅ *No ML used here, just insightful data analytics*

---

### 🔵 Phase 1: Smart Recommendation Using Given Waste Data

**🎯 Objective**  
Analyze full dataset with prepared, sold, and waste values, and suggest ideal preparation quantities using rolling averages and logic.

**🛠️ How it works**
- Upload dataset with: `Date`, `Item Name`, `Quantity_Prepared`, `Quantity_Sold`, `Quantity_Wasted`
- Standardizes item names
- Trains model to understand sales patterns
- Uses smart rules to recommend better prep quantities

✅ *Uses data cleaning + logic; no ML used*

---

### 🟠 Phase 2: Prediction of Sold Quantity Based on Prepared Quantity

**🎯 Objective**  
To predict sales when only the prepared quantity is known, using AI — so future prep numbers can be adjusted accordingly.

**🛠️ How it works**
- Upload dataset with: `Date`, `Item Name`, `Quantity_Prepared`
- Standardizes and processes input
- Applies trained Linear Regression model from Phase 1
- Predicts `Sold Quantity`, then calculates:
  - `Waste = Prepared - Predicted Sold`
  - `Recommended Quantity = Predicted Sold + buffer`

✅ *ML model is used here (Linear Regression)*

---

## 📊 Bonus Features

- Auto-generated visualizations:
  - 📉 Actual vs Predicted Sold/Waste
  - 🥗 Prepared vs Recommended Quantity
  - 🍽️ Waste per Item (bar + pie charts)
- GUI File Picker using **Tkinter**
- Output files saved as `.csv`
- User-friendly, school-level explanations

---

📌 All phases are implemented in **one Jupyter Notebook**, with clear section headers and comments to guide usage.


## 🙏 Acknowledgment

We sincerely thank our AI teacher, **Mrs. Karuna**, for guiding us throughout the project. Her support and feedback were instrumental in shaping this idea into a practical AI solution.  
We also appreciate our school for encouraging innovation and project-based learning.


***Thank you for reading!***
