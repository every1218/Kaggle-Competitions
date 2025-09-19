# Kaggle-Competitions

[![Kaggle](https://img.shields.io/badge/Kaggle-Learn-blue)](https://www.kaggle.com/competitions)
[![Made with Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Kaggle 대회에 참여한 학습기록 및 실습 노트북을 정리하는 레포지토리입니다.

완료(✅), 진행 중(🔥), 예정(📅)

---

## 📑 목차
- ✅ [01 - 타이타닉 생존자 예측](#-01---타이타닉-생존자-예측)
- 🔥 [02 - 보스턴 집값 예측]()

---

## 🚢 [01 - 타이타닉 생존자 예측](https://www.kaggle.com/competitions/titanic)

💻 **실습 노트북** : [Titanic - Machine Learning from Disaster](https://github.com/every1218/Kaggle-Competitions/tree/main/Titanic%20-%20Machine%20Learning%20from%20Disaster)

⏳ **학습 기간:** 25.06.24 ~ 25.07.13

🏁 **캐글 제출 점수:** `0.73923` 

📝 **진행 상태:** 완료(✅)


### 🧾 주요 기록
**1. EDA 가설 설정**
  - 여성 > 남성 생존률
  - 어린이, 1등석, 가족 동반자 생존률 ↑

**2. 시각화 확인**
  - 여성 > 남성 생존률
  -  `Sex`, `SibSp`, `Pclass`, `AgeGroup`별 생존률 시각화
  - `groupby().mean()`으로 수치 비교

**3. 전처리**
  - 결측치 처리: `Age`, `Fare`, `Embarked`
  - 특성 제거: `Name`, `Cabin`, `Ticket`
  - `Title` 추출 → `AgeGroup` 보정
  - 범주형 변수 숫자 인코딩
  - `Fare` → 사분위 구간화 (`FareBand`)

**4. 모델 성능 비교**
  - **Gradient Boostin**:	85.28%

---


## 🏠 [02 - 보스턴 집값 예측](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)

💻 **실습 노트북** : [House Prices - Advanced Regression Techniques]()

⏳ **학습 기간:**

🏁 **캐글 제출 점수:** 

📝 **진행 상태:** 진행 중(🔥)


### 주요 기록 
