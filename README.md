# 🛍️ Shopnest Store Analytics Dashboard (Power BI)

## 🚀 Overview
Developed an interactive Power BI dashboard to analyze customer behavior, sales performance, and order-level insights for Shopnest, an e-commerce platform. The solution enables data-driven decision-making by identifying top-performing products, delayed orders, and customer trends.

---

## 📊 Objective
To transform raw e-commerce data into actionable insights for:
- Revenue optimization  
- Inventory planning  
- Customer experience improvement  
- Order and delivery performance  

---

## 🛠️ Tools & Technologies
- Power BI  
- DAX (Data Analysis Expressions)  
- Power Query (ETL)  
- Data Modeling  

---

## 📌 Dashboard Analysis

### 🔹 Product Level Analysis
- Total Revenue: **$15.40M**  
- Total Sales: **13.59M units**  
- Average Review Score: **4.07**

**Insights:**
- Top-performing products contribute significantly to revenue  
- Categories like **Bed Bath Table** and **Health & Beauty** show higher delivery delays  
- Identified top and bottom rated products for quality improvement  

---

### 🔹 Order Level Analysis
- Compared **on-time vs delayed deliveries**
- Analyzed **monthly, quarterly, and yearly trends**

**Insights:**
- Majority orders delivered on time  
- Specific months show higher delays indicating operational inefficiencies  
- Seasonal trends observed in revenue performance  

---

### 🔹 Customer Level Analysis
- State-wise revenue distribution  
- Payment method analysis  

**Insights:**
- **São Paulo** is the highest revenue-generating region  
- **Credit Card (~74%)** is the dominant payment method  
- Customer behavior varies across acquisition channels  

---

## 📈 Key Metrics
- Total Revenue  
- Total Sales  
- Average Review Score  
- Delayed Orders  
- On-Time Delivery Rate  
- Revenue by Category & Location  

---

## 📐 Key DAX Measures

### 🔹 Total Revenue
```DAX
Total Revenue = 
SUM(Orders[Product_Price]) 

### 🔹 Delayed Orders 
Delayed Orders = 
CALCULATE(
    COUNT(Orders[Order_ID]),
    Orders[Actual_Delivery_Date] > Orders[Estimated_Delivery_Date]
)

🔹 On-Time Delivery %
On-Time Delivery % = 
DIVIDE(
    CALCULATE(
        COUNT(Orders[Order_ID]),
        Orders[Actual_Delivery_Date] <= Orders[Estimated_Delivery_Date]
    ),
    COUNT(Orders[Order_ID])
)
