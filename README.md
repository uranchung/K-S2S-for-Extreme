# Climate Extremes from ECMWF Hindcast

Initiative for Developing an East Asia Climate Extremes Dataset!

This repository provides ECMWF 2016 and 2024 Hindcast data on extreme events in East Asia, where **mean temperature(T2M)**, **sea surface temperature(SST)**, or **precipitation(TP)** exceed the 90th percentile.   
&nbsp;  
***Long-term Statistics of Climate Extremes:***  
&nbsp; 
&nbsp; 
&nbsp;&nbsp;**at version 2016:** *Maps of Annual Mean Occurrence at 90th Percentile for T2M, SST, PREC*  
<img width="194" height="300" alt="v16_t2m90th_Occurrence_AnnualMean_20yr_w3-mean_domin" src="https://github.com/user-attachments/assets/6ccc3fa9-e8e7-493e-a6b9-d1d6beafe01d" />
<img width="194" height="300" alt="v16_sst90th_Occurrence_AnnualMean_20yr_w3-mean_domin" src="https://github.com/user-attachments/assets/19adaaed-d22c-4d68-b1ab-b5b3edcb3264" />
<img width="194" height="300" alt="v16_tp90th_Occurrence_AnnualMean_20yr_w3-mean_domin" src="https://github.com/user-attachments/assets/44968cac-334b-4b1d-8023-3ef0cf90d60f" />  
&nbsp;  
&nbsp;  
&nbsp;&nbsp;**at 2024 version:** *Maps of Annual Mean Occurrence at 90th Percentile for T2M, SST, PREC*  
<img width="194" height="300" alt="t2m90th_Occurrence_AnnualMean_20yr_w3-mean_domin" src="https://github.com/user-attachments/assets/b18b7249-32dc-46a4-aa30-059476a0af28" /> 
<img width="194" height="300" alt="sst90th_Occurrence_AnnualMean_20yr_w3-mean_domin" src="https://github.com/user-attachments/assets/08a48f79-9213-4e5d-a4ba-9c871dc6cbe0" />
<img width="194" height="300" alt="tp90th_Occurrence_AnnualMean_20yr_w3-mean_domin" src="https://github.com/user-attachments/assets/1825ea6b-4ba7-461a-9a64-41fc86889fc7" />

&nbsp;




&nbsp;**at version 2016:** Maps of Annual Mean Intensity at 90th Percentile for T2M, SST, PREC at version 2024  

<img width="194" height="300" alt="t2m90pct_mean_intensity_map_20yr_2004_2023" src="https://github.com/user-attachments/assets/e42b0728-11b4-49dc-851c-5be5c9688a23" />
<img width="194" height="300" alt="sst90pct_mean_intensity_map_20yr_2004_2023" src="https://github.com/user-attachments/assets/8e198470-a3ed-4593-b2bd-16f198cfe0fb" />
<img width="194" height="300" alt="tp90pct_mean_intensity_map_20yr_2004_2023" src="https://github.com/user-attachments/assets/16f8b99d-c530-4846-a1d2-7a56e9b59371" />

&nbsp;&nbsp;

- 
## Data Download

  ```
  wget --content-disposition "https://www.dropbox.com/scl/fi/pqm64be2s46y8zpq0zn1e/EA1.5_P9095.zip?rlkey=rh8vnut3gzecn4472xycdr0da&st=63cbrbsl&dl=0"
  ```

***Spatial/Temporal Coverage***  

|         |Domain    |Resolution|
|---------|----------|----------|
|**Space**|21-48N, 114-141E|1.5deg|
|**Time** |1940-2024(ERA5), 1982-2024(OISST)|Daily / Weekly|
  
***Data format***   



## Contents  


***1. Climate Data*** 

|        |Description|
|--------|-----------|
|Frequency         |Daily/Weekly|
|Variables         |Mean Near Surface Temperature(T2M), Sea Surface Temperature(SST), Total Precipitation(TP)|
|Type              |Original Timeseries, Climatological Long-Term Mean, 90/95th Percentile Thresholds(p90/p95)|
|Resources         |ERA5, OISST(only for SST) and ECMWF-hindcast|
|Ref. Period       |1991-2020(ERA5/OISST, WMO recommendation), 2004-2023(ECMWF-hindcast)|


***2. Extreme Event Profile***

|        |Description|
|--------|-----------|
|Meta              |***Start/End Date, Duration, Mean/Peak Intensity*** and so forth|            
|Extreme Thresholds|p90, p95|            
|Event Criteria    |D3GG, D5G2 for *AHT/MHW* and D1G3, D3G3 for *HR*|

>*e.g., D3G5 represents minimum three-day **D**uration, permitting **G**aps of up to five days*  


***3. Period(Weekly/Monthly) Extremeness Metrics***  


|Metric         |Description|
|---------------|-----------|
|Extreme Days      |Number of days in the period when *T2M_e/TP_e/SST_e* exceed zero|
|Max. Intensity    |Peak *T2M_e/TP_e/SST_e* observed during the period|
|Impact Factor     |Cumulative *T2M_e/TP_e/SST_e* over the period|

>*T2M_e = T2M - thr; TP_e = TP - thr; SST_e = SST - thr*  


## How to use:   

### Codes for Data Processing and Visualization
&nbsp;&nbsp;&nbsp;&nbsp;if codes given: how to read the data and to isolate/plot timeseries of specific grid point?  
&nbsp;&nbsp;&nbsp;&nbsp;how about adding a table describing example codes given?  

### Ouput Details
&nbsp;&nbsp;&nbsp;&nbsp;if codes given: how to read the data and to isolate/plot timeseries of specific grid point?  
 
*for individual grid points within EA domain,*  
  
***1. Historical Event Statistics***  
- List of Events: *AHT, HR, MHW*  
- Event Statistics: Frequeny, Duration, Mean Intensity  
- Daily/Weekly Timeseries and Extremeness  

***2. Seasonality and Trend of Climate Extremes***  
- Seasonal Evolution of Event Frequency/Duration/Mean Intensity  
- Annual Timeseries of Frequency/Duration/Mean Intensity per Year and its Least-Squared Fitted Line


