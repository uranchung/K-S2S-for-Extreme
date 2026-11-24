

# 📊 사례 분석 (Case Study): Week 3 극한 고온 예측 비교

ECMWF Raw 앙상블과 딥러닝 기반 보정 모델(`Member-reg: no spread`, `Member-reg + MC dropout`, `Season-weighted mix`)의 선행 3주차(Week 3) TMAX 편차 및 P90 초과 확률 예측 성능을 ERA5 관측과 비교한 사례 분석입니다.

### 비교 대상 패널 구성 (왼쪽부터)
| 순서 | 모델 / 자료 | 설명 |
| :--- | :--- | :--- |
| 1 | **ERA5 (OBS)** | 재분석 관측 자료 (P90 초과 여부는 0 또는 1 이진값) |
| 2 | **ECMWF raw** | ECMWF 원시 앙상블 예측 |
| 3 | **Member-reg: no spread** | 멤버 회귀 기반 보정 모델 (스프레드 미반영) |
| 4 | **Member-reg + MC dropout** | 멤버 회귀 + Monte Carlo Dropout 적용 모델 |
| 5 | **Season-weighted mix** | 계절 가중 혼합 보정 모델 |

---

## 1. 사례 분석: 2025년 8월 말 고온 (`init: 2025-08-13`, Week 3)

**2025년 8월 28일에 시작하는 주** (2025년 8월 13일 초기화, 선행 3주차 / Week 3)를 분석했습니다.

* **TMAX 편차 (`°C`)**: 모든 방식이 북쪽(몽골·북중국)에 음의 편차를 예측했으나, `Season-weighted mix`는 그 폭이 `ECMWF raw`보다 작아 관측(ERA5)에 더 가까웠습니다. 한반도의 양의 편차도 다른 훈련 모델(`Member-reg`, `Member-reg + MC dropout`)보다 관측 및 ECMWF와 유사했습니다.
* **P90 초과 확률**: 관측(ERA5)에서 P90을 넘은 북쪽 영역을 `ECMWF raw`는 거의 0으로 예측했지만, `Season-weighted mix`는 0.2–0.4의 낮은 확률로나마 포착했습니다.

#### 그림 1-1. TMAX 편차 (`°C`)
<img width="3386" height="987" alt="Case_wk3_init20250813_anomaly" src="https://github.com/user-attachments/assets/e60a84bb-0a31-4ade-88ba-e9488606b0b3" />


#### 그림 1-2. P90 초과 확률 (관측은 초과 여부 0/1)
<img width="3386" height="947" alt="Case_wk3_init20250813_P90_event" src="https://github.com/user-attachments/assets/323d67a9-4cfd-49e0-9439-5e03fc63c62a" />


> **요약**: 2025년 8월 13일 초기화된 선행 3주차(8월 28일 시작 주간) 사례에서 `Season-weighted mix`는 몽골·북중국 지역의 과도한 음의 편차를 완화해 ERA5 관측 패턴에 근접한 기온 편차를 모의했습니다. 특히 관측(ERA5)에서 P90을 초과한 북부 영역을 `ECMWF raw`는 거의 0에 가까운 확률로 놓친 반면, `Season-weighted mix`는 0.2–0.4 수준의 확률 신호를 포착했으며 한반도 내 양의 편차 역시 안정적으로 유지했습니다.

---

## 2. 사례 분석: 2025년 10월 초 고온 (`init: 2025-09-17`, Week 3)

**2025년 10월 2일에 시작하는 주** (2025년 9월 17일 초기화, 선행 3주차 / Week 3, `2025-10-02 ~ 2025-10-08`)를 분석했습니다.

* **TMAX 편차 (`°C`)**: 관측(ERA5)에서는 중국 동부·남부, 몽골 동부·만주, 한반도, 일본 등 동아시아 전역에 걸쳐 강한 양의 기온 편차가 광범위하게 나타났습니다. `ECMWF raw`와 모든 보정 모델이 전반적인 양의 편차를 모의했으나 관측 대비 강도는 다소 과소모의하는 경향을 보였습니다. 그중 `Season-weighted mix`는 일본·동해 및 동아시아 북동부의 양의 편차 패턴을 안정적으로 유지하며 `ECMWF raw` 및 관측 패턴과 일관된 공간 분포를 나타냈습니다.
* **P90 초과 확률**: 관측(ERA5)에서 한반도, 일본, 중국 동부 및 주변 해역 대부분이 P90을 초과(1.0)했습니다. `Member-reg: no spread`는 서해·한반도 서부 등 특정 영역에 확률이 국지적으로 집중되는 경향을 보였고, `Member-reg + MC dropout`은 전반적으로 완만하게 퍼진 중간 수준 확률을 보였습니다. 반면 `Season-weighted mix`는 동해·일본 부근의 높은 확률 신호와 한반도·서해·중국 동부의 P90 초과 가능성을 과도한 국지적 왜곡 없이 균형 있게 포착했습니다.

#### 그림 2-1. TMAX 편차 (`°C`)
<img width="3386" height="987" alt="Case_wk3_init20250917_anomaly" src="https://github.com/user-attachments/assets/c28f8531-c979-4897-99b7-bffb69458883" />

#### 그림 2-2. P90 초과 확률 (관측은 초과 여부 0/1)
<img width="3386" height="947" alt="Case_wk3_init20250917_P90_event" src="https://github.com/user-attachments/assets/a0913807-df60-4ef9-9a85-417db6ff825b" />

> **요약**: 2025년 9월 17일 초기화된 선행 3주차(10월 2일 시작 주간) 사례에서 동아시아 전반의 광범위한 고온 현상에 대해 모든 모델이 양의 편차 경향을 포착했으나, 관측 대비 강도는 완만하게 모의되었습니다. P90 초과 확률에서는 `Season-weighted mix`가 일본·동해의 고확률 영역뿐만 아니라 한반도와 중국 동부의 초과 신호까지 국지적 편중 없이 균형 있게 예측했습니다.
