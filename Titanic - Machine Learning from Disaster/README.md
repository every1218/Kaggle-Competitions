# 🛳️ 타이타닉 생존자 예측 (Titanic - Machine Learning from Disaster)

타이타닉 탑승객 데이터를 기반으로 생존 여부를 예측하는 머신러닝 프로젝트입니다.  
캐글 초보자 튜토리얼에 맞춰 진행되었으며, 다양한 전처리 및 모델 비교를 통해 최적의 성능을 도출했습니다.

---

## 📂 데이터셋

- **train.csv** : 891명의 승객 정보 및 생존 여부 (`Survived`) 포함  
- **test.csv** : 418명의 승객 정보 (예측 대상)  
- 🔗 [데이터 출처 (Kaggle)](https://www.kaggle.com/competitions/titanic/data)

**📌 주요 변수 설명**
- `Pclass` : 객실 등급 (1~3등석)
- `Sex` : 성별
- `Age` : 나이
- `SibSp` : 형제자매/배우자 수
- `Parch` : 부모/자녀 수
- `Fare` : 운임 요금
- `Embarked` : 탑승 항구
- `Cabin`, `Ticket` : 분석에서 제외

---

## 📊 분석 과정

### 1. EDA & 가설 설정
- 여성이 남성보다 생존률이 높을까?
- 어린이, 1등석, 가족 동반자는 생존 확률이 높을까?

### 2. 시각화
- `Sex`, `SibSp`, `Pclass`, `AgeGroup`별 생존률 시각화
- `groupby().mean()`으로 통계 확인

### 3. 전처리
- 결측치 처리: `Age`, `Fare`, `Embarked`
- 텍스트 변수 제거: `Name`, `Cabin`, `Ticket`
- 호칭(`Title`) 추출 → `AgeGroup` 보정
- 범주형 변수 인코딩 (`Sex`, `Embarked`, `Title`, `AgeGroup`)
- `Fare`는 구간화(`FareBand`) 후 수치로 변환

---

## 🛠 사용 기술 스택

| 분류 | 사용 도구 |
|------|-----------|
| 언어 | Python |
| 데이터 분석 | Pandas, Numpy |
| 시각화 | Matplotlib, Seaborn |
| 전처리 | 문자열 처리, 결측값 보간, 범주형 인코딩 |
| 모델링 | Scikit-learn (`sklearn`) |
| 사용 모델 | Naive Bayes, Logistic Regression, Support Vector Machine, Decision Tree / Random Forest, K-Nearest Neighbors, Perceptron, SGD Classifier, Gradient Boosting

---

## 📈 모델 성능 비교

| 모델 | 정확도 (Accuracy) |
|------|-------------------|
| ✅ Gradient Boosting | **85.28%** |
| SVM | 83.25% |
| Random Forest | 83.25% |
| KNN | 82.74% |
| Logistic Regression | 80.20% |
| Decision Tree | 79.70% |
| Linear SVC | 79.19% |
| Gaussian NB | 78.68% |
| SGD | 78.68% |
| Perceptron | 76.65% |

---

## 📁 제출 파일 생성

```python
# 그래디언트 부스팅 분류기로 예측
ids = test['PassengerId']
predictions = gbk.predict(test.drop('PassengerId', axis=1))

# 제출 파일 생성
output = pd.DataFrame({ 'PassengerId': ids, 'Survived': predictions })
output.to_csv('submission.csv', index=False)
