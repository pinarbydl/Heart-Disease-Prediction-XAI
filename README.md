<details>
  <summary>Türkçe </summary>

  # Kalp Hastalığı Tahmini ve Açıklanabilir Yapay Zeka (XAI) Analizi

Bu projede, kalp hastalığı veri seti kullanılarak makine öğrenmesi modelleri geliştirilmiş ve bu modellerin tahminleri Açıklanabilir Yapay Zeka (XAI) yöntemleriyle analiz edilmiştir. Projenin amacı yalnızca yüksek doğruluklu tahminler yapmak değil, aynı zamanda modellerin hangi özelliklere dayanarak bu tahminleri yaptığına dair içgörü sunmaktır.

---

## 📌  Proje Açıklaması

Çalışmada, bir hastanın yaş, kolesterol, kan basıncı gibi çeşitli tıbbi özelliklerine dayanarak kalp hastalığına sahip olup olmadığını tahmin eden sınıflandırma modelleri oluşturulmuştur. Modellerin performansları Accuracy, ROC AUC, F1-Score gibi metriklerle değerlendirilmiş ve en başarılı model, hiperparametre optimizasyonu ile daha da geliştirilmiştir.

Projenin temel odak noktası, bu modellerin “kara kutu” yapısını açıklığa kavuşturmaktır. SHAP, LIME ve Permutation Importance gibi XAI teknikleri ile şu sorulara yanıt aranmıştır:

- Modelin tahminlerinde en etkili özellikler hangileridir?
- Bir özelliğin artması veya azalması kalp hastalığı riskini nasıl etkiler?
- Belirli bir hasta için yapılan tahminin arkasındaki nedenler nelerdir?

---

## 📊 Veri Seti

Projede, kalp hastalığı teşhisine yönelik 14 değişken içeren, eksiksiz ve hazır bir veri seti kullanılmıştır.

**Değişkenler:**
- `age`: Yaş
- `sex`: Cinsiyet (1 = erkek; 0 = kadın)
- `cp`: Göğüs ağrısı tipi
- `trestbps`: Dinlenme kan basıncı
- `chol`: Kolesterol
- `fbs`: Açlık kan şekeri > 120 mg/dl (1 = evet; 0 = hayır)
- `restecg`: Dinlenme EKG sonuçları
- `thalach`: Maksimum kalp atış hızı
- `exang`: Egzersize bağlı anjina (1 = evet; 0 = hayır)
- `oldpeak`: Egzersize bağlı ST depresyonu
- `slope`: ST segmentinin eğimi
- `ca`: Floroskopi ile renklendirilen damar sayısı
- `thal`: Talasemi tipi
- `condition`: Kalp hastalığı durumu (1 = hasta; 0 = sağlıklı) – Hedef değişken

---

## ⚙️ Metodoloji

### 1. Keşifsel Veri Analizi (EDA)
Veri seti görselleştirme teknikleriyle analiz edilmiş, aykırı değerler kontrol edilmiş ve her bir özelliğin hedef değişken üzerindeki etkisi incelenmiştir.

### 2. Modelleme
Aşağıdaki sınıflandırma modelleri eğitilmiştir:
- CatBoost Classifier
- LightGBM Classifier
- XGBoost Classifier

### 3. Model Değerlendirme
Modeller, Accuracy, ROC AUC, Recall, Precision ve F1-Score gibi metriklerle karşılaştırılmıştır.

### 4. Hiperparametre Optimizasyonu
En iyi performansı gösteren CatBoost modeli, GridSearchCV yöntemi ile optimize edilmiştir.

---

## 🧠 Açıklanabilir Yapay Zeka (XAI) Yöntemleri

Model tahminlerini anlamlandırmak için şu XAI yöntemleri kullanılmıştır:

- **SHAP (SHapley Additive exPlanations):** Oyun teorisine dayalı olarak her bir özelliğin modele katkısını hesaplar. Hem genel (summary plot) hem de bireysel (waterfall plot) açıklamalar sağlar.

- **LIME (Local Interpretable Model-agnostic Explanations):** Herhangi bir modelin tekil bir tahminini yerel olarak yorumlar. Belirli bir tahminin neden verildiğini ve hangi özelliklerin etkili olduğunu görselleştirir.

- **Permutation Importance:** Bir özelliğin değerleri karıştırılarak modelin performansındaki değişime bakılır. Performans düşüşü, o özelliğin önem derecesini gösterir.

---

## 📈 Sonuçlar

Modelleme ve optimizasyon sürecinin ardından CatBoost modeli en iyi performansı göstermiştir. XAI analizleri, özellikle thal, cp, ca ve oldpeak değişkenlerinin kalp hastalığı tahmininde belirleyici rol oynadığını ortaya koymuştur.

SHAP ve LIME analizleri, modelin hem genel anlamda hangi özniteliklere dayandığını hem de bireysel bazda verilen tahminlerin nedenlerini başarılı bir şekilde açıklamıştır.

Bu proje, Açıklanabilir Yapay Zeka yöntemlerinin makine öğrenmesi modellerine nasıl yorumlanabilirlik ve güvenilirlik kattığını gösteren etkili bir örnek sunmaktadır.

</details>



# Heart Disease Prediction and Explainable AI (XAI) Analysis

This project develops machine learning models using a heart disease dataset and interprets the predictions of these models through Explainable Artificial Intelligence (XAI) techniques. The goal is not only to achieve high prediction accuracy but also to gain insights into which features the model relies on when making decisions.

---

## 📌 Project Overview

In this study, classification models were developed to predict whether a patient has heart disease based on various medical features such as age, cholesterol level, and blood pressure. The models were evaluated using performance metrics like Accuracy, ROC AUC, and F1-Score, and the best-performing model was further improved through hyperparameter tuning.

The primary focus of the project is to illuminate the "black-box" nature of machine learning models. XAI methods such as SHAP, LIME, and Permutation Importance were used to answer the following questions:

- Which features are most influential in the model's predictions?
- How does an increase or decrease in a feature affect heart disease risk?
- What are the key reasons behind a specific prediction for an individual?

---

## 📊 Dataset

A publicly available dataset containing 14 attributes related to heart disease diagnosis was used. The dataset is clean and ready for analysis, with no missing values.

**Features:**
- `age`: Age
- `sex`: Gender (1 = male; 0 = female)
- `cp`: Chest pain type
- `trestbps`: Resting blood pressure
- `chol`: Serum cholesterol
- `fbs`: Fasting blood sugar > 120 mg/dl (1 = yes; 0 = no)
- `restecg`: Resting electrocardiographic results
- `thalach`: Maximum heart rate achieved
- `exang`: Exercise-induced angina (1 = yes; 0 = no)
- `oldpeak`: ST depression induced by exercise
- `slope`: Slope of the peak exercise ST segment
- `ca`: Number of major vessels colored by fluoroscopy
- `thal`: Thalassemia
- `condition`: Heart disease status (1 = has disease; 0 = healthy) – Target variable

---

## ⚙️ Method Used

### 1. Exploratory Data Analysis (EDA)
The dataset was explored using visualizations to detect outliers and understand the distribution of features in relation to the target variable.

### 2. Modeling
The following classification models were trained:
- CatBoost Classifier
- LightGBM Classifier
- XGBoost Classifier

### 3. Model Evaluation
The models were compared using metrics such as Accuracy, ROC AUC, Recall, Precision, and F1-Score.

### 4. Hyperparameter Optimization
The best-performing model (CatBoost) was further optimized using GridSearchCV.

---

## 🧠 Explainable AI (XAI) Techniques

To interpret the model predictions, the following XAI techniques were applied:

- **SHAP (SHapley Additive exPlanations):** Based on game theory, SHAP calculates the contribution of each feature to the model's output. It provides both global (summary plot) and local (waterfall plot) explanations.

- **LIME (Local Interpretable Model-agnostic Explanations):** Interprets individual predictions of any machine learning model locally, showing which features were most important for a specific prediction.

- **Permutation Importance:** Assesses feature importance by measuring the decrease in model performance when feature values are randomly shuffled.

---
## 📈 Results

After model training and optimization, the CatBoost model achieved the best performance. XAI analysis revealed that features such as thal, cp, ca, and oldpeak were particularly important in predicting heart disease.

SHAP and LIME outputs successfully explained both the global feature importance and the key drivers behind individual predictions.

This project serves as a practical example of how XAI methods can bring transparency and interpretability to machine learning models in the healthcare domain.
