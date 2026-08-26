# ❤️ Heart Disease Prediction

## 🌐 Live Demo

🚀 **Try the application:**  
[Heart Disease Prediction App](https://raja-singh-rajput-heart-disease.streamlit.app)

A Machine Learning web application that predicts the **risk of heart disease** based on a patient's clinical and cardiac-related information.

The project uses **Logistic Regression** as the machine learning model and **Streamlit** to provide an interactive web interface for making predictions.

---

## 📌 Project Overview

Heart disease is one of the major health concerns worldwide. Early identification of potential risk can help in taking appropriate medical attention and preventive measures.

In this project, a machine learning classification model is trained on heart disease data. The complete workflow includes:

* Data loading and exploration
* Data cleaning and preprocessing
* Exploratory Data Analysis (EDA)
* Categorical feature encoding
* Feature scaling
* Logistic Regression model training
* Model evaluation
* Saving the trained model and preprocessing objects
* Building an interactive Streamlit application
* Making predictions on new patient input

> **Disclaimer:** This project is intended for educational and demonstration purposes only. It is not a medical diagnostic tool and should not be used as a substitute for professional medical advice.

---

## 🎯 Objective

The main objective of this project is to build a classification model that predicts whether a person is at **higher risk of heart disease** based on the provided clinical features.

### Target Variable

`HeartDisease`

* `0` → Lower risk / No heart disease
* `1` → Higher risk / Heart disease

---

## 📊 Dataset

The dataset contains clinical and cardiac information for patients.

### Features

| Feature          | Description                                           |
| ---------------- | ----------------------------------------------------- |
| `Age`            | Age of the patient                                    |
| `Sex`            | Sex of the patient                                    |
| `ChestPainType`  | Type of chest pain                                    |
| `RestingBP`      | Resting blood pressure                                |
| `Cholesterol`    | Cholesterol level                                     |
| `FastingBS`      | Whether fasting blood sugar is greater than 120 mg/dL |
| `RestingECG`     | Resting electrocardiogram result                      |
| `MaxHR`          | Maximum heart rate achieved                           |
| `ExerciseAngina` | Exercise-induced angina                               |
| `Oldpeak`        | ST depression induced by exercise                     |
| `ST_Slope`       | Slope of the peak exercise ST segment                 |
| `HeartDisease`   | Target variable                                       |

### Sample Data

| Age | Sex | ChestPainType | RestingBP | Cholesterol | FastingBS | RestingECG | MaxHR | ExerciseAngina | Oldpeak | ST_Slope | HeartDisease |
| --: | :-: | :-----------: | --------: | ----------: | --------: | :--------: | ----: | :------------: | ------: | :------: | -----------: |
|  40 |  M  |      ATA      |       140 |         289 |         0 |   Normal   |   172 |        N       |     0.0 |    Up    |            0 |
|  49 |  F  |      NAP      |       160 |         180 |         0 |   Normal   |   156 |        N       |     1.0 |   Flat   |            1 |
|  37 |  M  |      ATA      |       130 |         283 |         0 |     ST     |    98 |        N       |     0.0 |    Up    |            0 |
|  48 |  F  |      ASY      |       138 |         214 |         0 |   Normal   |   108 |        Y       |     1.5 |   Flat   |            1 |
|  54 |  M  |      NAP      |       150 |         195 |         0 |   Normal   |   122 |        N       |     0.0 |    Up    |            0 |

---

## 🔎 Exploratory Data Analysis

The dataset was explored to understand:

* Distribution of numerical features
* Distribution of categorical features
* Relationship between input features and the target variable
* Correlation between numerical variables
* Possible outliers and unusual observations
* Class distribution of the target variable

The complete EDA and preprocessing workflow can be found in:

📓 **`Heart_Disease.ipynb`**

---

## ⚙️ Data Preprocessing

Before training the model, the data was prepared using the following steps:

### 1. Categorical Encoding

Categorical variables such as:

* `Sex`
* `ChestPainType`
* `RestingECG`
* `ExerciseAngina`
* `ST_Slope`

were converted into numerical representations using one-hot encoding.

For example:

```text
Sex
M → Sex_M
F → Sex_F
```

### 2. Feature Scaling

Numerical features were scaled before being passed to the Logistic Regression model.

A scaler was trained on the training data and saved as:

```text
scaler_heart.pkl
```

The same scaler is used by the Streamlit application when processing new patient input.

### 3. Column Alignment

The final feature columns used during model training were saved as:

```text
columns_heart.pkl
```

This ensures that the input provided through Streamlit has the **same feature structure and column order** as the training data.

---

## 🤖 Machine Learning Model

### Logistic Regression

The project uses **Logistic Regression** for binary classification.

The model predicts one of two classes:

```text
0 → Lower Risk
1 → Higher Risk
```

The trained model is saved as:

```text
Logistic_heart.pkl
```

Using a saved model allows the Streamlit application to make predictions without retraining the model every time the application starts.

---

## 🧠 Prediction Workflow

The Streamlit application follows this workflow:

```text
User Input
    ↓
Create DataFrame
    ↓
Categorical Feature Encoding
    ↓
Match Training Columns
    ↓
Feature Scaling
    ↓
Logistic Regression Model
    ↓
Prediction
    ↓
Display Result
```

### Prediction Output

If the model predicts:

```text
1
```

the application displays:

> ⚠️ High Risk of Heart Disease

If the model predicts:

```text
0
```

the application displays:

> ✅ Low Risk of Heart Disease

---

## 🖥️ Streamlit Application

The project includes an interactive Streamlit interface where users can enter:

* Age
* Sex
* Chest Pain Type
* Resting Blood Pressure
* Cholesterol
* Fasting Blood Sugar
* Resting ECG
* Maximum Heart Rate
* Exercise-Induced Angina
* Oldpeak
* ST Slope

After clicking **Predict**, the application processes the input and displays the predicted risk.

---

## 🛠️ Technologies Used

### Programming Language

* Python

### Libraries

* **Pandas** — Data manipulation and analysis
* **NumPy** — Numerical computations
* **Scikit-learn** — Machine learning and preprocessing
* **Joblib** — Saving and loading trained ML objects
* **Matplotlib** — Data visualization
* **Seaborn** — Statistical visualization
* **Streamlit** — Interactive web application

### Development Tools

* Google Colab — Model development and experimentation
* VS Code — Application development
* Git & GitHub — Version control and project hosting

---

## 📁 Project Structure

```text
Heart_disease/
│
├── app.py
│
├── Heart_Disease.ipynb
│
├── heart.csv
│
├── Logistic_heart.pkl
├── scaler_heart.pkl
├── columns_heart.pkl
│
├── requirements.txt
├── README.md
├── .gitignore
│
└── .venv/
```

### File Description

| File                  | Purpose                                                     |
| --------------------- | ----------------------------------------------------------- |
| `app.py`              | Streamlit web application                                   |
| `Heart_Disease.ipynb` | Data analysis, preprocessing, model training and evaluation |
| `heart.csv`           | Dataset                                                     |
| `Logistic_heart.pkl`  | Trained Logistic Regression model                           |
| `scaler_heart.pkl`    | Saved feature scaler                                        |
| `columns_heart.pkl`   | Saved training feature columns                              |
| `requirements.txt`    | Python dependencies                                         |
| `.gitignore`          | Files/folders excluded from Git                             |
| `.venv/`              | Local Python virtual environment                            |

> `.venv/` is used locally and should **not** be uploaded to GitHub.

---

## 🚀 How to Run the Project Locally

### 1. Clone the Repository

```bash
git clone <your-repository-url>
```

### 2. Open the Project

```bash
cd Heart_disease
```

### 3. Create a Virtual Environment

```bash
python -m venv .venv
```

### 4. Activate the Virtual Environment

#### Windows CMD

```cmd
.venv\Scripts\activate.bat
```

#### Windows PowerShell

```powershell
.\.venv\Scripts\Activate.ps1
```

### 5. Install Dependencies

```bash
pip install -r requirements.txt
```

### 6. Run the Streamlit Application

```bash
python -m streamlit run app.py
```

The application will open in your browser.

---

## 📈 Model Pipeline

```text
                  HEART DISEASE DATASET
                           │
                           ▼
                    Data Exploration
                           │
                           ▼
                         EDA
                           │
                           ▼
                  Data Preprocessing
                           │
              ┌────────────┴────────────┐
              ▼                         ▼
       Categorical Encoding       Numerical Features
              │                         │
              └────────────┬────────────┘
                           ▼
                     Feature Scaling
                           │
                           ▼
                  Logistic Regression
                           │
                           ▼
                    Model Evaluation
                           │
                           ▼
                   Save Model (.pkl)
                           │
                           ▼
                  Streamlit Application
                           │
                           ▼
                    User Prediction
```

---

## 🔐 Saved Model Components

Instead of saving only the trained classifier, this project saves three important components:

### `Logistic_heart.pkl`

Contains the trained Logistic Regression model.

### `scaler_heart.pkl`

Contains the scaler used during model training.

### `columns_heart.pkl`

Contains the expected feature columns and their order.

Keeping these preprocessing components is important because new data must be transformed in **the same way as the training data** before making predictions.

---

## 📌 Key Learning Outcomes

Through this project, the following concepts were implemented:

* Data preprocessing
* Exploratory Data Analysis
* Categorical variable encoding
* Feature scaling
* Binary classification
* Logistic Regression
* Model serialization using Joblib
* Consistent preprocessing during inference
* Streamlit application development
* Virtual environments
* Project dependency management
* Git and GitHub project organization

---

## 🔮 Future Improvements

Possible improvements for this project include:

* Comparing Logistic Regression with KNN, Decision Tree, Random Forest and SVM
* Hyperparameter tuning
* Cross-validation
* Adding probability-based predictions
* Adding model performance visualizations
* Improving the UI/UX of the Streamlit application
* Deploying the application online
* Adding more robust input validation
* Adding explainability techniques such as feature importance or SHAP

---

## ⚠️ Disclaimer

This application is created for **educational and machine learning demonstration purposes**.

The predictions generated by this application should **not be considered medical advice or a medical diagnosis**. Real medical decisions should always be made by qualified healthcare professionals using appropriate clinical evaluation.

---

## 👨‍💻 Author

**Raja Singh Rajput**

Built as a Machine Learning + Streamlit project to demonstrate an end-to-end classification workflow from data preprocessing and model training to deployment through an interactive web application.

---

## ⭐ If You Like This Project

If you find this project useful or interesting, consider giving the repository a ⭐ on GitHub.
