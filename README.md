# Climate Extremes from ECMWF Hindcast

## ECMWF Hindcast 버전2016과 버전2024 자료에서 한반도를 포함한 동아시아 지역의 극한 정보 표출!

이 repository에서는 ECWMF 버전 2016과 버전 2024의 Hindcast 자료를 기반으로 동아시아 지역에서 **평균기온**, **해수면 온도**, **강수**가 90퍼센타일(예, T2M>=90 percentile)을 초과하는 이상 발생 정보(예, 발생 빈도 및 발생 강도 등)를 제공한다.  
(English) This repository provides ECMWF 2016 and 2024 Hindcast data on extreme events in East Asia, where mean temperature, sea surface temperature, or precipitation exceed the 90th percentile.  
&nbsp;  
***Spatial/Temporal Coverage for ECMWF Hindcast***  

|               |Domain     |Resolution|
|---------------|-----------|----------|
|**Space**      |21-48N, 114-141E|1.5deg|
|**Time**       |1940-2024(ERA5), 1982-2024(OISST)|Daily / Weekly|
|**Data format**|NetCDF |
|**Data download**| Google drive|

&nbsp;  
***입력 자료 설명:***  
&nbsp;&nbsp;&nbsp;&nbsp;자료1: ECMWF Hindcast의 각 버전(버전 2016과 버전 2024)의 평균 기온(T2M), 해수면온도(SST), 강수(PREC) 자료에서 3주(15일~21일)에 해당하는 일 자료로 재구성한 자료임  
|data1(nc file) information|
|---------------------------------------------|
|Dimensions: (time: 7140, latitude: 72, longitude: 72) |
|Coordinates:|
|&nbsp;&nbsp;&nbsp;&nbsp;* time (time) datetime64[ns] 57kB 2004-01-19 2004-01-20 ... 2024-01-15|
|&nbsp;&nbsp;&nbsp;&nbsp;* latitude (latitude) float64 576B 57.0 55.5 54.0 52.5 ... -46.5 -48.0 -49.5|
|&nbsp;&nbsp;&nbsp;&nbsp;* longitude (longitude) float64 576B 52.5 54.0 55.5 ... 156.0 157.5 159.0|
|Data variables:|
|&nbsp;&nbsp;&nbsp;&nbsp;t2m (time, latitude, longitude) float32 148MB|  
  
(※ ECMWF Hindcast의 초기 날짜는 버전마다 다름)  
&nbsp;  
&nbsp;&nbsp;&nbsp;&nbsp;자료2: 자료 1에서 ECMWF Hindcast의 버전 2016과 버전 2024의 초기 날짜(forecast issued date) 기반으로 T2M, SST, PREC에서 90퍼센타일을 초과하는 이상 발생 정보, 예를 들면, 90퍼센타일을 초과하는 날에 대한 평년 빈도 및 평년 강도를 계산한 자료임  
|data2(nc file) information|
|---------------------------------------------|
|Dimensions: (latitude: 72, longitude: 72, doy: 356) |
|Coordinates:|
|&nbsp;&nbsp;&nbsp;&nbsp;* latitude (latitude) float64 576B 57.0 55.5 54.0 ... -46.5 -48.0 -49.5|
|&nbsp;&nbsp;&nbsp;&nbsp;* longitude (longitude) float64 576B 52.5 54.0 55.5 ... 156.0 157.5 159.0|
|&nbsp;&nbsp;&nbsp;&nbsp; quantile      float64 8B ...|
|&nbsp;&nbsp;&nbsp;&nbsp;* doy (doy) int64 3kB 1 3 4 5 6 7 8 ... 360 361 362 363 364 365 366|
|Data variables:|
|&nbsp;&nbsp;&nbsp;&nbsp;t2m_clim90th (doy, latitude, longitude) float64 15MB|  
  
&nbsp;  
  
***자료(nc files)를 plot하는 방법:***  
&nbsp;&nbsp;&nbsp;&nbsp;예제 코드 1: [90퍼센타일을 초과하는 날에 대한 평년 빈도 및 평년 강도 맵]  
&nbsp;&nbsp;&nbsp;&nbsp;자료 1에서 ECMWF Hindcast의 버전 2016과 버전 2024의 초기 날짜(forecast issued date) 기반으로 90퍼센타일을 초과하는 이상 발생 정보, 예를 들면, 90퍼센타일을 초과하는 날에 대한 평년 빈도 및 평년 강도를 계산해서 (맵으로) 표출했다.  
<img width="200" height="325" alt="plot_v2024_t2m_90th_frequency_test" src="https://github.com/user-attachments/assets/f3140b0d-2056-4b78-90f0-348a96d35e6e" />
<img width="200" height="325" alt="plot_v2024_t2m_90th_intensity_test" src="https://github.com/user-attachments/assets/3693c368-b78a-4a20-964a-e7ef9f202713" />

&nbsp;&nbsp;&nbsp;&nbsp;예제 코드 2: [90퍼센타일을 초과하는 날에 대한 선 그래프]  
&nbsp;&nbsp;&nbsp;&nbsp;또한, 자료 1과 2를 이용해서 초기 날짜 기반으로 2023년 (버전 2016의 경우 2012년)에서 90퍼센타일을 초과하는 날에 대한 선 그래프를 표출했다.  
&nbsp;&nbsp;&nbsp;&nbsp;버전 2024년의 경우, 2004년부터 2023년까지의 평년 평균 기온은 초록색 선, 90퍼센타일을 초과하는 평년 평균 기온은 빨강색 선, 2023년의 평균 기온은 검정색 선으로 표출했는데, 이때, 2023년 대비 90퍼센타일을 초과하는 평년 평균 기온을 초과하는 경우에 대해서는 빨강색 면적으로 표출했다.  
<img width="600" height="525" alt="Lineplot_t2m_90th_Extreme2023" src="https://github.com/user-attachments/assets/5f9933aa-630a-43c2-9ba9-28c430cda32d" />


