# Ride Order Failure Analysis — Key Insights

## 1. Failure Distribution by Category

| Failure Category | Orders | Insight |
|---|---|---|
| User Cancelled - No Driver Assigned | 13,435 | Highest failure category; customers cancel mainly due to no driver assignment |
| System Reject - No Driver Assigned | 9,469 | Large number of failures occur before driver matching |
| User Cancelled - Driver Assigned | 8,360 | Driver assignment reduces cancellation count significantly |
| System Reject - Driver Assigned | 4 | System is highly reliable after driver assignment |

---

## 2. Failed Orders by Hour

| Hour | Failed Orders | Insight |
|---|---|---|
| 8 AM | ~3,900 | Highest failure spike due to morning rush-hour demand |
| 9 PM | ~2,800 | High night-time failures likely due to reduced driver availability |
| 11 PM | ~2,500 | Late-night demand causes elevated cancellations |
| 12 AM | ~2,000 | High midnight failure volume indicates supply-demand imbalance |
| 5 AM | ~120 | Lowest failures due to low demand and better driver availability |

---

## 3. Failure Categories During Peak Hours

### 8 AM Breakdown

| Category | Orders | Insight |
|---|---|---|
| User Cancelled - No Driver | ~1,450 | Driver shortage is the primary failure reason |
| System Reject - No Driver | ~1,340 | Matching system struggles during peak load |
| User Cancelled - Driver Assigned | ~1,080 | Driver assignment improves ride retention |

---

## 4. Average Cancellation Time

| Scenario | Avg Cancellation Time | Insight |
|---|---|---|
| Driver Assigned | 150–370 sec | Customers wait longer once a driver is assigned |
| No Driver Assigned | 90–140 sec | Users cancel quickly without driver confirmation |

### Peak Waiting Hours

| Hour | Cancellation Time | Insight |
|---|---|---|
| 3 AM | ~370 sec | Users wait longer at night due to fewer alternatives |
| 11 PM | ~320 sec | Lower driver availability increases waiting time |
| 6–7 PM (No Driver) | ~85–90 sec | Fast cancellations during evening rush hours |

---

## 5. ETA Analysis

| Hour | Avg ETA | Insight |
|---|---|---|
| 8 AM | ~675 sec | Highest ETA caused by peak traffic and demand |
| 7 AM | ~645 sec | Morning congestion increases delivery time |
| 5 PM | ~550 sec | Evening rush contributes to longer ETAs |
| 4 AM | ~270 sec | Lowest ETA due to minimal traffic |
| 8 PM | ~300 sec | Improved road conditions reduce ETA |

---

## 6. Key Business Conclusions

- Driver assignment delay is the primary operational bottleneck.
- Peak commute hours generate the highest order failures.
- Higher ETA strongly correlates with higher cancellation rates.
- Customers are significantly more patient after driver assignment.
- Ride failures are concentrated during morning and evening rush hours.
