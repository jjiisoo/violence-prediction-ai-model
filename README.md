# 음성 데이터에서 폭력 감지를 위한 1D-2D 비교 및 모델 최적화

**🏆2024년 한국인공지능융합기술학회 우수 발표 논문상 수상**

---

현대 사회에서 일상 속 폭력 상황이 빈번하게 발생하면서, 이를 실시간으로 탐지하는 기술의 필요성이 커지고 있다. 기존 영상 기반 방법은 CCTV 사각지대 등에서 한계가 존재하지만, 오디오는 이러한 시각적 제약을 극복할 수 있다.
본 연구는 음성 데이터를 활용하여 일상생활 속 폭력적 소리와 비폭력적 소리를 실시간으로 구분하는 모델을 제안하며,
1D·2D 모델 비교와 최적화를 통해 다양한 환경에서 높은 성능과 안정성을 달성하고자 한다.

## Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white) ![Librosa](https://img.shields.io/badge/Librosa-000000?style=for-the-badge&logo=python&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white) ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white) ![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)

---

## 데이터 구성

### 1️⃣ 데이터 수집

- **영어 데이터:**  
  - 출처: *Kaggle – Audio-based Violence Detection Dataset*  
  - 특징: 전체 데이터 중 일부만 선별하여 사용  

- **한국어 데이터:**  
  - 출처: *YouTube에서 직접 수집*  
  - 특징: 실생활 대화 및 뉴스 음성 등 폭력적 상황이 포함된 영상을 활용해 폭력 음성만 추출  

---

### 2️⃣ 데이터 전처리

- 모든 음성 데이터를 **3초 단위로 통일**
- **Train / Validation / Test** 세트로 구분

#### 📊 폭력 데이터
| 구분 | 개수 |
|------|------|
| Train | 1,014개 |
| Validation | 370개 |
| Test | 67개 |

#### 📊 비폭력 데이터
| 구분 | 개수 |
|------|------|
| Train | 832개 |
| Validation | 244개 |
| Test | 76개 |

---

### 3️⃣ 데이터 정제 및 변환

- **노이즈/무음 제거:**  
  - noisereduce와 pydub 라이브러리를 활용해 노이즈 제거 및 무음 제거 

- **파일 형식 변환:**  
  - `mp3` → `wav` 변환  
  - `wav`는 손실 압축이 없어 더 정밀한 분석 가능  

---
