# 🔥 Forest Fire Weather Index (FWI) Prediction System

A Machine Learning web application that predicts the **Fire Weather Index (FWI)** using environmental and meteorological data.

The project combines data preprocessing, feature engineering, model training, and deployment into a complete end-to-end pipeline using **Ridge Regression** and **Flask**.

---

## 🚀 Project Overview

Wildfires are strongly influenced by weather conditions and fuel moisture levels.

This system predicts wildfire intensity risk using:

- Temperature
- Humidity
- Wind Speed
- Rainfall
- Fire Index Indicators

The prediction is based on historical wildfire data from two regions in Algeria.

Users can input environmental values through a web interface and get an estimated **FWI score**, which indicates wildfire risk.

---

## 📊 Dataset

**Algerian Forest Fires Dataset**

Includes:

- 244 observations
- 2 Regions:
  - Bejaia
  - Sidi Bel-Abbes
- Time Period: June 2012 – September 2012

---

## 🧠 Machine Learning Pipeline

### 1. Data Cleaning
- Removed null values
- Fixed column formatting
- Converted data types
- Removed redundant date columns
- Encoded fire classes into binary values

---

### 2. Feature Engineering
- Created Region column
- Converted categorical fire labels into numeric form
- Dropped highly correlated features using correlation threshold (> 0.85)

Final Features Used:

```

Temperature
RH
Ws
Rain
FFMC
DMC
ISI
Classes
Region

```

Target Variable:

```

FWI (Fire Weather Index)

```

---

### 3. Feature Scaling
Used:

```

StandardScaler

```

To normalize feature ranges before training.

---

### 4. Models Trained

- Linear Regression
- Lasso Regression
- Ridge Regression
- ElasticNet

After evaluation, **Ridge Regression** was selected for deployment.

---

### 5. Model Deployment

The following components were serialized using Pickle:

- Trained Ridge Model → `ridge.pkl`
- Feature Scaler → `scalar.pkl`

---

## 🌐 Web Application

Built using:

- Flask
- HTML + CSS

Users enter environmental inputs and receive predicted FWI score instantly.

---

## 📥 User Inputs Required

- Temperature
- RH (Relative Humidity)
- Ws (Wind Speed)
- Rain
- FFMC
- DMC
- ISI
- Classes (Fire / Not Fire → encoded)
- Region (0 or 1)

---

## 📤 Output

Predicted:

```

Fire Weather Index (FWI)

```

Higher values indicate higher wildfire risk.

---

## 🛠 Tech Stack

- Python
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib / Seaborn
- Flask
- HTML / CSS

---

## 🧩 Project Structure

```

├── models/
│   ├── ridge.pkl
│   └── scalar.pkl
│
├── templates/
│   ├── index.html
│   └── home.html
│
├── app.py
├── notebook.ipynb
└── README.md

````

---

## ▶️ Running the Project

### 1. Install Dependencies

```bash
pip install -r requirements.txt
````

### 2. Run Flask App

```bash
python application.py
```

## 📈 Future Improvements

* Add model explainability (SHAP)
* Add live weather API integration
* Deploy to cloud
* Add classification-based fire risk category

---
