# 🛒 Blinkit Sales Dashboard (Power BI Project)

Analyze Blinkit's order data, customer trends, and delivery performance using Power BI.  
This dashboard helps visualize key metrics like sales by city, delivery time, product category performance, and more.

---

## 🛠️ Tools Used
- Power BI Desktop
- DAX Measures
- Excel (Data Cleaning)
- GitHub

---

## 📊 Dashboard Insights

- 📍 **Top Cities by Sales**
- 🕐 **Average Delivery Time**
- 🛍️ **Most Popular Product Categories**
- 📦 **Total Orders & Delayed Deliveries**
- 📈 **Sales Trends Over Time**

---

## 📂 Dataset Info

Files used:
- `blinkit_orders.csv`
- `blinkit_order_items.csv`
- `blinkit_products.csv`
- `blinkit_customers.csv`
- `blinkit_delivery_performance.csv`

---

## 📌 Key Measures (DAX)

```DAX
Total Orders = COUNT('blinkit_orders'[order_id])

Total Revenue = SUMX('blinkit_order_items', 'blinkit_order_items'[quantity] * 'blinkit_order_items'[price])

Avg Delivery Time = AVERAGE('blinkit_delivery_performance'[delivery_time_minutes])

Delayed Orders = CALCULATE([Total Orders], 'blinkit_delivery_performance'[delivery_status] = "Delayed")