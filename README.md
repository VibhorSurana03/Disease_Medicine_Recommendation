# 🏥 AI-Powered Disease & Medicine Recommendation System

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-Web_Framework-000000?style=for-the-badge&logo=flask&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

**An intelligent healthcare assistant that predicts diseases and recommends personalized treatment plans**

[Features](#-features) • [How It Works](#-how-it-works) • [Installation](#-installation) • [Tech Stack](#-tech-stack)

</div>

---

## 🌟 Overview

This AI-powered healthcare system uses machine learning to predict diseases based on symptoms and provides comprehensive treatment recommendations including medications, diet plans, workout routines, and precautions. The system also features a medicine recommendation engine that suggests alternative medications based on similarity analysis.

---

## ✨ Features

### 🔍 **Disease Prediction**
- **Symptom-Based Diagnosis** - Input multiple symptoms to get accurate disease predictions
- **Support Vector Classification (SVC)** - Advanced ML model with high accuracy
- **132+ Symptoms Database** - Comprehensive symptom dictionary
- **41 Disease Categories** - Wide range of disease classifications

### 💊 **Comprehensive Treatment Plans**
- **Medication Recommendations** - Specific medicines for diagnosed conditions
- **Diet Plans** - Personalized dietary suggestions for recovery
- **Workout Routines** - Exercise recommendations tailored to conditions
- **Precautions** - Important safety measures and lifestyle changes
- **Disease Descriptions** - Detailed information about diagnosed conditions

### 🔬 **Medicine Recommendation Engine**
- **Similarity-Based Suggestions** - Find alternative medicines using ML
- **Autocomplete Search** - Quick medicine lookup with intelligent suggestions
- **User Feedback System** - Collect and store user feedback for improvements
- **Large Medicine Database** - Extensive pharmaceutical database

### 🎨 **User-Friendly Interface**
- **Modern Bootstrap UI** - Clean, professional interface with Bootstrap 5.3
- **Responsive Design** - Works seamlessly on desktop, tablet, and mobile devices
- **Modal-Based Results** - Interactive modals for disease, description, precautions, medications, workouts, and diets
- **Speech Recognition** - Voice input support for symptom entry (browser-based Web Speech API)
- **Autocomplete Search** - jQuery UI autocomplete for medicine search (min 2 characters)
- **Buy Medicine Links** - Direct links to PharmEasy for purchasing recommended medicines
- **Feedback System** - AJAX-based feedback collection saved to CSV file
- **Autocomplete Search** - jQuery UI autocomplete for medicine names
- **Direct Purchase Links** - Quick links to buy recommended medicines online

---

## 🧠 How It Works

### Disease Prediction Pipeline
1. **Input Symptoms** - User enters comma-separated symptoms
2. **Preprocessing** - Symptoms are normalized and vectorized
3. **ML Prediction** - SVC model predicts the most likely disease
4. **Data Retrieval** - System fetches relevant treatment information
5. **Display Results** - Comprehensive treatment plan is presented

### Medicine Recommendation Pipeline
1. **Medicine Selection** - User searches and selects a medicine
2. **Similarity Calculation** - System computes similarity scores
3. **Top Recommendations** - Returns 5 most similar alternatives
4. **Feedback Collection** - Users can rate recommendations

---

## 🛠️ Tech Stack

### **Machine Learning**
- **Scikit-Learn** - SVC model for disease classification
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations
- **Pickle** - Model serialization

### **Web Framework**
- **Flask** - Lightweight Python web framework
- **Jinja2** - Template engine for dynamic HTML rendering
- **Bootstrap 5.3** - Responsive CSS framework
- **jQuery 3.6** - JavaScript library for AJAX and DOM manipulation
- **jQuery UI 1.13** - Autocomplete widget for medicine search
- **Web Speech API** - Browser-based speech recognition (webkit)

### **Data Processing**
- **CSV Datasets** - Structured medical data
- **Feature Engineering** - Symptom vectorization
- **Data Normalization** - Preprocessing pipelines

### **Development Tools**
- **Jupyter Notebook** - Model development and experimentation
- **Python 3.8+** - Core programming language

---

## 📦 Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)

### Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone https://github.com/VibhorSurana03/Disease_Medicine_Recommendation.git
   cd Disease_Medicine_Recommendation
   ```

2. **Create Virtual Environment** (Recommended)
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install flask pandas numpy scikit-learn
   ```
   
   Note: `pickle` is part of Python's standard library, no separate installation needed.

4. **Verify Dataset Files**
   Ensure the following files are in the `dataset/` directory:
   - `symtoms_df.csv`
   - `precautions_df.csv`
   - `workout_df.csv`
   - `description.csv`
   - `medications.csv`
   - `diets.csv`
   - `Training.csv`

5. **Train Models and Create Model Files**
   
   The project requires trained models that need to be created first:
   
   **Option A: Train from Jupyter Notebooks**
   ```bash
   # Install Jupyter if not already installed
   pip install jupyter notebook
   
   # Run the notebooks to train models
   jupyter notebook
   ```
   
   Open and run these notebooks in order:
   - `Medicine Recommendation System.ipynb` - Trains the disease prediction model
   - `medicine-recommend.ipynb` - Creates medicine similarity model
   
   **Option B: Create models directory manually**
   
   Create a `models/` directory and ensure it contains:
   - `svc.pkl` - Disease prediction SVC model (trained on Training.csv)
   - `medicine_dict.pkl` - Medicine database dictionary
   - `similarity.pkl` - Medicine similarity matrix
   
   These files are generated by running the Jupyter notebooks.

6. **Run the Application**
   ```bash
   python main.py
   ```

7. **Access the Application**
   Open your browser and navigate to: `http://localhost:5000`
   
   **Available Routes:**
   - `/` - Home page (Disease Prediction)
   - `/predict` - Disease prediction endpoint (POST)
   - `/recommend` - Medicine recommendation page
   - `/autocomplete` - Medicine autocomplete API (GET)
   - `/feedback` - Feedback submission endpoint (POST)
   
   **Note:** Routes for `/about`, `/contact`, `/developer`, and `/blog` are defined but templates don't exist yet.

---

## 🎯 Usage

### Disease Prediction
1. Navigate to the home page
2. **Enter symptoms** in one of two ways:
   - Type symptoms separated by commas (e.g., "itching, skin_rash, nodal_skin_eruptions")
   - Click "Start Speech Recognition" to speak your symptoms
3. Click "Predict" button
4. View results in interactive modals:
   - **Disease** - Predicted disease name
   - **Description** - Detailed disease information
   - **Precaution** - 4 safety measures to follow
   - **Medications** - Recommended medicines
   - **Workouts** - Exercise recommendations
   - **Diets** - Dietary suggestions

**Note**: Symptoms must match the exact format in the database (use underscores instead of spaces, e.g., "high_fever" not "high fever")

### Medicine Recommendation
1. Click "Medicine" in the navigation bar
2. Start typing a medicine name (autocomplete suggestions appear after 2 characters)
3. Select the medicine from dropdown suggestions
4. Click "Recommend Medicine" button
5. View 5 similar alternative medicines with:
   - Medicine names
   - "Buy Here" links to PharmEasy for each medicine
6. **Provide Feedback** (optional):
   - Select "Yes" or "No" for helpfulness
   - Add optional comments
   - Click "Submit Feedback" (saves to `feedback_data.csv`)

---

## 📊 Dataset Information

The system uses multiple curated datasets:

- **Training Dataset** - 4920+ symptom-disease mappings
- **Symptom Severity** - Weighted symptom importance
- **Descriptions** - Detailed disease information
- **Medications** - Disease-specific medicine recommendations
- **Diets** - Nutritional guidelines per disease
- **Workouts** - Exercise recommendations
- **Precautions** - Safety measures and lifestyle changes
- **Medicine Database** - Comprehensive pharmaceutical data

---

## 🔬 Model Performance

- **Algorithm**: Support Vector Classification (SVC)
- **Features**: 132 symptom indicators
- **Classes**: 41 disease categories
- **Training Strategy**: Stratified sampling for balanced classes
- **Validation**: 70-30 train-test split

---

## 🚀 Future Enhancements

- [ ] Complete the additional pages (About, Contact, Developer, Blog)
- [ ] Deep learning models for improved accuracy
- [ ] Multi-language support
- [ ] Mobile application
- [ ] Integration with electronic health records
- [ ] Symptom severity analysis with weighted scoring
- [ ] Doctor consultation booking
- [ ] Prescription management
- [ ] Health tracking dashboard
- [ ] Improve speech recognition accuracy
- [ ] Add symptom suggestion dropdown
- [ ] User authentication and history tracking

---

## ⚠️ Disclaimer

**This system is for educational and informational purposes only. It should NOT be used as a substitute for professional medical advice, diagnosis, or treatment. Always consult with qualified healthcare providers for medical concerns.**

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

---

---

## 👨‍💻 Developer

**Vibhor Surana**

- GitHub: [@VibhorSurana03](https://github.com/VibhorSurana03)
- Email: vibhorsurana03@gmail.com

---

<div align="center">

**⭐ If this project helped you, please give it a star!**

*Empowering healthcare with AI* 🏥💡

</div>
