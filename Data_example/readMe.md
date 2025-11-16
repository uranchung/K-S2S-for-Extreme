# 🌏 ECMWF Hindcast Extreme Events over East Asia

These data 1 and 2 provide ECMWF Hindcast (versions 2016 and 2024) data focusing on **extreme events** in East Asia,  
where mean temperature (T2M), sea surface temperature (SST), or precipitation (PREC) exceed the **90th percentile** threshold.

---

***Spatial/Temporal Coverage***  

|         |Domain    |Resolution|
|---------|----------|----------|
|**Space**|21-48N, 114-141E|1.5deg|
|**Time** |1940-2024(ERA5), 1982-2024(OISST)|Daily / Weekly|

&nbsp;  
***Data format***   
  
&nbsp;
## Contents (-> Data? or Data Description)

***1. Climate Data*** 

|        |Description|
|--------|-----------|
|Frequency         |Daily/Weekly|
|Variables         |Mean Near Surface Temperature(T2M), Sea Surface Temperature(SST), Total Precipitation(TP)|
|Type              |Original Timeseries, Climatological Long-Term Mean, 90/95th Percentile Thresholds(p90/p95)|
|Resources         |ERA5, OISST(only for SST) and ECMWF-hindcast|
|Ref. Period       |1991-2020(ERA5/OISST, WMO recommendation), 2004-2023(ECMWF-hindcast)|  

&nbsp;  

## 📦 Input Data Description

### **Data 1**
NetCDF files reconstructed from ECMWF Hindcast versions **2016** and **2024**, containing:
- Mean temperature (T2M)
- Sea surface temperature (SST)
- Precipitation (PREC)

For each forecast initialization date, data corresponding to **lead week 3 (days 15–21 after initialization)**  
were extracted and reorganized into daily records.

### **Data 2**  
Based on *Data 1*, 90th-percentile climatological thresholds (`t2m_clim90th`) were computed for each ECMWF Hindcast version using the forecast issued dates.  
