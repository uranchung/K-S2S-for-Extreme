# 🌍Climate Extremes from ECMWF Hindcast 🌍

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
&nbsp;&nbsp;&nbsp;&nbsp;자료1: ECMWF Hindcast의 각 버전(버전 2016과 버전 2024)의 **평균기온(T2M)**, **해수면온도(SST)**, **강수(PREC)** 자료에서 예측 초기일(forecast issued date) 이후 **3번째 주(lead week, 15일~21일)에** 해당하는 **주별(day-of-week)자료**를 추출하여 재구성한 NetCDF 파일임  
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
&nbsp;&nbsp;&nbsp;&nbsp;자료2: 자료 1을 바탕으로 ECMWF Hindcast의 버전별 초기일(forecast issued date) 기준으로 일자별 90퍼센타일을 평년값을 계산하여 구성한 파일임(아래 정보는 T2M에 대한 것임)  
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
&nbsp;&nbsp;&nbsp;&nbsp;**예제 코드 1:** [90퍼센타일을 초과 빈도 및 강도 맵]  
&nbsp;&nbsp;&nbsp;&nbsp;자료1과 2를 바탕으로 ECMWF Hindcast의 버전 2016과 버전 2024 자료(자료1)에서 각 예측일의 평균기온(T2M)을 자료2의 90퍼센타일(기준)과 비교하여, 90퍼센타일을 초과하는 날의 빈도와 초과 강도를 계산하여 지도로 표출하였음.  
<img width="200" height="325" alt="plot_v2024_t2m_90th_frequency_test" src="https://github.com/user-attachments/assets/f3140b0d-2056-4b78-90f0-348a96d35e6e" />
<img width="200" height="325" alt="plot_v2024_t2m_90th_intensity_test" src="https://github.com/user-attachments/assets/3693c368-b78a-4a20-964a-e7ef9f202713" />

&nbsp;&nbsp;&nbsp;&nbsp;**예제 코드 2:** [90퍼센타일 초과 선 그래프]  
&nbsp;&nbsp;&nbsp;&nbsp;또한, 특정 연도(예: 2023년, 버전 2024 기준)의 3주간(15~21일) 7일의 일별 평균기온(T2M)을 평년값(90퍼센타일-기준)과 비교하여 선 그래프로 나타냄. 그래서, 특정 연도의 이상고온 구간을 시각적으로 보여줌  
&nbsp;&nbsp;&nbsp;&nbsp;초록색 선: 2004–2023년 평년 평균 기온  
&nbsp;&nbsp;&nbsp;&nbsp;빨강색 선: 2004–2023년 90퍼센타일 초과 평년값  
&nbsp;&nbsp;&nbsp;&nbsp;검정색 선: 2023년 평균 기온  
&nbsp;&nbsp;&nbsp;&nbsp;빨간 면적: 2023년 평균 기온이 90퍼센타일 초과 평년값보다 높은 구간  



