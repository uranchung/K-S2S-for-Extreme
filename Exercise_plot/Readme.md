
---

## 🧮 Example Codes

### **Example Code 1 — Maps of Frequency and Intensity Above the 90th Percentile**

Using *Data 1* and *Data 2*, this code:
1. Compares each day’s mean temperature (T2M) against the 90th-percentile climatological threshold (`t2m_clim90th`);
2. Calculates  
   - **Frequency (%)** — proportion of days exceeding the threshold  
   - **Intensity** — mean anomaly of exceedances;
3. Visualizes results as **spatial maps** showing regional patterns of extreme events across East Asia (including the Korean Peninsula).

🗺️ *Result:* A heat map showing how often and how strongly each region experienced extreme warm or wet conditions.

---

### **Example Code 2 — Time-Series Plot of 90th-Percentile Exceedance**

This code generates a line plot illustrating the temporal evolution of mean temperature for a specific year  
(e.g., **2023** for version 2024 or **2012** for version 2016), compared with climatological thresholds:

| Line Color | Meaning |
|-------------|----------|
| 🟩 Green | Climatological mean temperature (2004–2023) |
| 🟥 Red | 90th-percentile climatological mean temperature (2004–2023) |
| ⚫ Black | Observed mean temperature for 2023 |
| 🟥 Shaded Red | Periods when 2023 temperature exceeded the 90th-percentile threshold |

📈 *Result:* Highlights the duration and magnitude of extreme-temperature periods relative to the climatological baseline.

---

## 🌐 Spatial & Temporal Coverage

| Parameter | Details |
|------------|----------|
| **Domain** | 21–48° N, 114–141° E |
| **Resolution** | 1.5° × 1.5° |
| **Period** | 1996–2015 (ver. 2016), 2004–2023 (ver. 2024) |
| **Time Step** | Weekly (lead week 3 = 15–21 days) |
| **Format** | NetCDF |

---

## 🗃️ Data Sources

- ECMWF Hindcast datasets (Versions 2016 & 2024)  
- Processed for regional analysis of **East Asian extreme events**

---

## 📊 Output Examples

**Example Code 1:**  
Map of 90th-percentile exceedance frequency and intensity

**Example Code 2:**  
Line plot showing 2023 mean temperature vs. climatological thresholds

---

> 🧠 *Note:*  
> This repository focuses on comparative diagnostics between ECMWF 2016 and 2024 Hindcast versions  
> for East Asian extreme events, emphasizing the climatological behavior of the 90th-percentile exceedance.


