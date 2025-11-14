# 🌏 ECMWF Hindcast Extreme Events over East Asia

These six NetCDF data provide ECMWF Hindcast (versions 2016 and 2024) data focusing on **extreme events** in East Asia,  
where mean temperature (T2M), sea surface temperature (SST), or precipitation (PREC) exceed the **90th percentile** threshold.

---

## 📦 Input Data Description

### **Data 1**
NetCDF files reconstructed from ECMWF Hindcast versions **2016** and **2024**, containing:
- Mean temperature (T2M)
- Sea surface temperature (SST)
- Precipitation (PREC)

For each forecast initialization date, data corresponding to **lead week 3 (days 15–21 after initialization)**  
were extracted and reorganized into daily records.

### **Data 2**  
Based on data 1, the file is composed by calculating the normal value of 90 percentile by date based on the initial date of each version of ECMWF Hindcast.  
