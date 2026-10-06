# 🚴‍♂️ Swiggy Delivery Time Prediction

An end-to-end Machine Learning project that predicts food delivery time based on order, partner, environmental, and traffic features. Built with **scikit-learn** and deployed as an interactive web dashboard using **Streamlit**.

---

## 📌 Project Overview

Accurate delivery time prediction is critical for food delivery platforms to set customer expectations and optimize logistics. This project trains and deploys a Machine Learning regression model that estimates the total time taken (in minutes) for delivery given real-time order factors.

---

## 🛠️ Tech Stack & Libraries

- **Language:** Python
- **Machine Learning:** `scikit-learn` (Pipeline, ColumnTransformer, RandomForestRegressor)
- **Data Manipulation & Analysis:** `pandas`, `numpy`
- **Model Serialization:** `joblib`
- **Web App / UI:** `streamlit`

---

## 📂 Project Structure

```plaintext
├── app.py                  # Streamlit web application
├── model.pkl               # Trained ML pipeline (preprocessing + Random Forest Regressor)
├── requirements.txt        # Python package dependencies
├── swiggy.ipynb            # Jupyter Notebook with EDA, preprocessing, and model training
├── swiggy_cleaned (1).csv  # Cleaned dataset used for training and UI dropdown options
├── .gitignore              # Ignored files (virtual environment, cache, etc.)
└── README.md               # Project documentation
```

---

## ⚙️ Model Pipeline

The predictive pipeline (`model.pkl`) uses a Scikit-Learn `Pipeline` composed of:
1. **Data Preprocessing (`ColumnTransformer`):**
   - **Nominal Encoding (`OneHotEncoder`):** Vehicle type, festival, city type, order day, weekend flag.
   - **Ordinal Encoding (`OrdinalEncoder`):** Weather condition (`sunny` → `stormy`), Traffic density (`low` → `jam`).
   - **Feature Scaling (`StandardScaler`):** Delivery partner ratings, vehicle condition, multiple deliveries, pickup time, and distance.
2. **Regressor:**
   - **Random Forest Regressor** trained to predict estimated delivery time in minutes.

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/julavikram11-commits/Swiggy-Delivery-Time-Prediction.git
cd Swiggy-Delivery-Time-Prediction
```

### 2. Create and Activate a Virtual Environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Streamlit Application
```bash
streamlit run app.py
```

The app will launch in your browser at `http://localhost:8501`.

---

## 📊 Features & Inputs

The Streamlit web interface allows users to input:
- **Delivery Partner Info:** Age, Rating, Vehicle Type, Vehicle Condition
- **Order Characteristics:** Order Type, Multiple Deliveries, Order Time (Hour / Time of Day)
- **Geographic & Route Factors:** Delivery Distance (km), City Type, City Name
- **Environmental Factors:** Weather condition, Traffic level, Festival status, Weekend indicator
