# Ride Order Failure Analysis 🚖📊

## Project Overview
This project analyzes failed ride orders to identify operational bottlenecks, cancellation behavior, ETA trends, and peak failure hours using Python data analysis and visualization libraries.

The analysis focuses on:
- Ride cancellation patterns
- Driver assignment impact
- Hourly failure distribution
- ETA trends
- Customer waiting behavior

---

# Data Source

Dataset Source:  
https://platform.stratascratch.com/data-projects/insights-failed-orders

---

# Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn

---

# Project Objectives

- Analyze failed ride orders
- Identify peak failure hours
- Understand driver assignment impact
- Analyze cancellation timing
- Study ETA trends and operational inefficiencies

---
<img width="859" height="470" alt="image" src="https://github.com/user-attachments/assets/3ebc18a0-923b-4c6a-a993-a589fd190340" />


# Key Insights

## 1. Driver Assignment Bottleneck
- Analyzed **31,268 failed ride orders**
- **43% (13,435 orders)** were caused by **user cancellations before driver assignment**
- Driver allocation delay was identified as the largest operational bottleneck

---

## 2. System Reliability After Driver Matching
- Only **4 orders (<0.02%)** failed after driver assignment
- **99.98% of failures occurred before successful driver matching**
- Indicates extremely high operational reliability once a driver is assigned

---

## 3. Peak Hour Failure Spike
- Highest failures occurred at **8 AM (~3,900 failed orders)**
- Failure volume was **32× higher** than the lowest-demand hour at **5 AM (~120 orders)**
- Morning rush hour created the most severe demand-supply imbalance

---

## 4. Customer Patience & ETA Impact
- Customers waited **2.6× longer** after driver assignment (**150–370 sec**) compared to rides without assignment (**90–140 sec**)
- Peak ETA reached **~675 sec at 8 AM**
- High ETA strongly correlated with increased cancellations

---

# Visualizations Included

- Failure distribution by category
- Failed orders by hour
- Failure categories by hour
- Average cancellation time analysis
- ETA trend analysis

---

# Sample Analysis Code

## Failure Distribution by Category

```python
orders_count['label'] = (
    orders_count['order_status'] + " - " + orders_count['driver_assigned']
)

plt.figure(figsize=(10,5))

bars = plt.bar(
    orders_count['label'],
    orders_count['order_gk']
)

plt.bar_label(bars)

plt.xlabel(
    "Order Status & Driver Assignment",
    fontsize=12,
    fontweight='bold'
)

plt.ylabel(
    "Order Count",
    fontsize=12,
    fontweight='bold'
)

plt.title(
    "Status and Driver Assignment Wise Order Distribution",
    fontsize=14,
    fontweight='bold'
)

plt.grid(True, linestyle='--', alpha=0.4)

plt.show()
```

---

## Failed Orders by Hour

```python
merged.groupby(by='hour')['order_gk'].count().plot(
    figsize=(10, 5),
    legend=True,
    xticks=range(0, 24),
    title='Count of Failed Orders by Hour of Day'
)

plt.xlabel('Hour of Day')
plt.ylabel('Failed Orders')

plt.grid(True, linestyle='--', alpha=0.4)

plt.show()
```

---

## Average Cancellation Time

```python
sb.lineplot(
    data=merged,
    x='hour',
    y='cancellations_time_in_seconds',
    hue='driver_assigned',
    estimator='mean'
)

plt.title(
    "Average Time to Cancellation Per Hour and Driver Assignment"
)

plt.xticks(range(0, 24))

plt.grid(True, linestyle='--', alpha=0.4)

plt.show()
```

---

# Business Conclusions

- Driver assignment delay is the primary contributor to failed rides
- Peak-hour demand significantly increases ride cancellations
- Higher ETA directly impacts cancellation probability
- Driver assignment improves customer retention and patience
- Ride failures are heavily concentrated during rush hours

---

# Resume Worthy Highlights

- Performed exploratory data analysis on 31K+ failed ride orders
- Built operational KPI visualizations using Pandas, Matplotlib, and Seaborn
- Identified peak-hour cancellation and ETA patterns
- Derived business insights from ride-order operational data
- Analyzed customer waiting behavior and driver assignment efficiency

---

# Author

Udit Narayan Kaushik
