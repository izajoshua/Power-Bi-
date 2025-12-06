# **Complete Interpretation of All Charts – Hospital Services Dashboard**

---

# **📌 Page 1: Executive Overview — Chart Interpretations**

<img width="811" height="627" alt="image" src="https://github.com/user-attachments/assets/939d414f-d5e0-485d-b70e-c7031f9b730b" />


## **1. KPI Cards (Executive Metrics)**

### **Layman**

These numbers tell how the hospital is performing overall — how busy it is, how satisfied patients and staff are, and how many patients came and left.

### **Technical**

KPIs calculated using DAX measures:

* **Total Admitted:** SUM of all admissions
* **Bed Utilization %:** Total occupied beds ÷ total capacity
* **Avg Satisfaction & Morale:** Averages of survey values
* **Turnover Rate:** Discharges ÷ Admissions
* **Overall Service Score:** Weighted blend of satisfaction (60%) + morale (40%)

**What it means:**
The hospital is **very busy**, operating at **~92% bed occupancy**, with moderately high patient satisfaction and adequate staff morale.

---

## **2. Bar Chart: Sum of Patients Admitted by Week**


### **Layman**

Shows which weeks were the busiest. Tall bars = more admissions.

### **Technical**

Columns represent the **weekly sum of admissions** (week 1–52).
Helps identify seasonal peaks or operational pressure periods.

---

## **3. Bed Utilization % by Service**


### **Layman**

Shows which services are full:

* Emergency and General Medicine are nearly full.
* ICU has some space left.

### **Technical**

A horizontal bar chart displaying the **bed utilization percentage** for each service.
Conditional formatting highlights high-pressure areas (>90%) in red.

---

# **📌 Page 2: Service Performance & Capacity Pressure**
<img width="1335" height="720" alt="image" src="https://github.com/user-attachments/assets/8cb6186f-c576-45b7-a5a7-bc12d3cc43a9" />


## **1. Bed Utilisation % + Avg Available Beds Table**

### **Layman**

Shows how full each department is.
Even though some have many beds, they are almost always occupied.

### **Technical**

Displays two measures:

* **Utilization %**
* **Average available beds**

Combining these highlights whether high utilization is because of:

* Small bed count
* Large bed count but high demand

---

## **2. Staff Morale by Service (Bar Chart)**

### **Layman**

Almost no data or very low values — indicates missing survey responses or filtered-out results.

### **Technical**

Clustered bar chart expecting averages of staff morale by service.

---

## **3. Combo Chart: Avg Patient Satisfaction vs Avg Staff Morale**

### **Layman**

Tells how patients and staff feel:

* ICU → happiest patients, lowest staff morale
* Emergency → lowest patient satisfaction, highest staff morale
* Satisfaction decreases with crowding

### **Technical**

* **Line:** Avg patient satisfaction
* **Bars:** Avg staff morale
* Dual-axis to compare correlations.

---

# **📌 Page 3: Admission Trends**
<img width="1068" height="631" alt="image" src="https://github.com/user-attachments/assets/a68b586a-c99c-4657-a42e-89d376bb6296" />

## **1. Weekly Admissions Trend (Line Chart)**

### **Layman**

Admissions go up and down throughout the year but recently increased sharply — the hospital is busier now than before.

### **Technical**

* X-axis: Week #
* Y-axis: Sum of Admissions
* Rolling Average smooths data
  Shows long-term upward trend → increasing operational load.

---

## **2. Admissions by Service (Column Chart)**

### **Layman**

General Medicine admits the most patients by far.

### **Technical**

Shows total admissions grouped by service, sorted descending.

---

## **3. Requests vs Admissions (Stacked Bar + Line)**

### **Layman**

Most weeks:

* Patients who requested admission were actually admitted.

Only recently gaps appear, meaning requests > capacity.

### **Technical**

Compares:

* **Requests (bars)**
* **Actual admissions (line)**

A narrowing or widening gap shows pressure on the system.

---

## **4. Turnaway Rate % by Week (Line Chart)**
<img width="1065" height="635" alt="image" src="https://github.com/user-attachments/assets/f198d9c1-cfc9-43fc-b6c5-939d88fb0782" />


### **Layman**

One of the most important charts.
Shows the percentage of patients the hospital could NOT admit because beds were full.

* Many weeks show **high rates: 60–80%**
* Indicates the hospital is unable to meet demand regularly
* Late-year spike shows extreme pressure

### **Technical**

Formula typically:

```
Turnaway Rate % = (Requests – Admissions) / Requests
```

The line’s volatility shows instability in bed capacity.

---

# **📌 Page 4: Length of Stay (LOS) Distribution**

## **Length of Stay Histogram**

### **Layman**

Shows how long patients typically stay:

* High bars at 1–3 days → short treatments common
* Bars at 5–7 days → medium care
* Bars after 10 days → long-term or complex cases
* Smooth decline → normal pattern
* Random spikes → treatment-specific stay durations

### **Technical**

* X-axis: Days stayed
* Y-axis: Number of patients
  Used to analyze bed occupancy patterns and predict flow.

---

# **📌 Page 5: Discharges Trend Chart**

## **Weekly Discharges Trend (Line Chart)**

### **Layman**

Shows how many patients leave the hospital each week:

* Peaks = more discharges → more beds freed
* Lows = poor bed turnover → congestion

### **Technical**

* Weekly aggregation of discharges
  Used alongside admissions to detect imbalance.

---

# **📌 Page 6: Turnaway Rate — Deep Interpretation**

### **Layman Summary**

The hospital runs out of beds frequently.
Turnaway spikes (above 70%) mean:

* Patients diverted
* Emergency strain
* Longer waiting times
* Increased risk

Mid-year dips show relief in demand, but year-end spikes show crisis.

### **Technical Summary**

The volatile week-to-week pattern confirms:

* Poor alignment of supply vs. demand
* Bed capacity bottlenecks
* Seasonal demand patterns
* Discharge scheduling impacts
* Insufficient buffer for emergencies

---

# ⭐ **Overall Insights (Simple Version)**

* The hospital is extremely busy — beds are nearly always full.
* Admissions increasing throughout the year → rising demand.
* High turnaway spikes show severe capacity shortages.
* General Medicine + Emergency face the most pressure.
* Patient satisfaction drops when services are crowded.
* ICU gives the best patient experience but staff are exhausted.
* Length of stay impacts bed turnover significantly.

---

# ⭐ **Overall Insights (Technical Version)**

* Utilization consistently >90% → no operational buffer.
* Turnaway Rate rising to 60–80% → supply-demand mismatch.
* LOS distribution indicates mixed short and medium stays influencing occupancy.
* Admissions exceeding discharges → cumulative bed pressure.
* Service-level variance shows ICU strain, ED overload.
* Forecasting required: weekly patterns highly seasonal and volatile.


