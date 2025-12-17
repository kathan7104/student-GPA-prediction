# Student GPA Prediction

A data-driven machine learning project that predicts student Grade Point Average (GPA) based on various factors including demographic information, study habits, parental involvement, and extracurricular activities.

## 📋 Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Features](#features)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Data Preprocessing](#data-preprocessing)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Model Training](#model-training)
- [Results](#results)
- [Key Findings](#key-findings)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)

## 🎯 Overview

This project aims to predict student GPA using machine learning techniques. By analyzing various factors that influence academic performance, the model can help educators and administrators identify students who may need additional support and understand the key factors contributing to academic success.

## 📊 Dataset

The dataset contains **2,392 student records** with **15 features** covering:
- Student demographics (Age, Gender, Ethnicity)
- Parental background (Education level, Support level)
- Study habits (Weekly study time, Absences, Tutoring)
- Extracurricular activities (Sports, Music, Volunteering)
- Academic performance (GPA, Grade Class)

### Dataset Features

#### Student Information
- **StudentID**: Unique identifier for each student (1001 to 3392)

#### Demographic Details
- **Age**: Student age ranging from 15 to 18 years
- **Gender**: 0 = Male, 1 = Female
- **Ethnicity**: 
  - 0 = Caucasian
  - 1 = African American
  - 2 = Asian
  - 3 = Other

#### Parental Background
- **ParentalEducation**: 
  - 0 = None
  - 1 = High School
  - 2 = Some College
  - 3 = Bachelor's
  - 4 = Higher
- **ParentalSupport**: 
  - 0 = None
  - 1 = Low
  - 2 = Moderate
  - 3 = High
  - 4 = Very High

#### Study Habits
- **StudyTimeWeekly**: Weekly study time in hours (0-20)
- **Absences**: Number of absences during school year (0-30)
- **Tutoring**: 0 = No, 1 = Yes

#### Extracurricular Activities
- **Extracurricular**: 0 = No, 1 = Yes
- **Sports**: 0 = No, 1 = Yes
- **Music**: 0 = No, 1 = Yes
- **Volunteering**: 0 = No, 1 = Yes

#### Academic Performance
- **GPA**: Grade Point Average (2.0 to 4.0) - **Target Variable**
- **GradeClass**: Classification based on GPA
  - 0 = 'A' (GPA ≥ 3.5)
  - 1 = 'B' (3.0 ≤ GPA < 3.5)
  - 2 = 'C' (2.5 ≤ GPA < 3.0)
  - 3 = 'D' (2.0 ≤ GPA < 2.5)
  - 4 = 'F' (GPA < 2.0)

## 📁 Project Structure

```
student-GPA-prediction/
│
├── STD_performance.ipynb          # Main analysis notebook
├── Student_performance_data _.csv  # Original dataset
└── cleaned_dataset.csv            # Preprocessed dataset
```

## 🛠️ Technologies Used

- **Python 3.x**
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **Matplotlib & Seaborn**: Data visualization
- **Scikit-learn**: Machine learning models and evaluation
  - Linear Regression
  - Random Forest Regressor
  - StandardScaler
  - Train-test split
- **SciPy**: Statistical analysis

## 🔧 Data Preprocessing

1. **Missing Value Handling**:
   - Numerical columns: Filled with median values
   - Categorical columns: Filled with mode values

2. **Data Validation**:
   - Age: Filtered to 15-18 years (high school range)
   - GPA: Validated to 0-4.0 scale
   - Absences: Limited to 0-30 per term
   - StudyTimeWeekly: Validated to 0-20 hours

3. **Duplicate Removal**: Removed duplicate StudentID entries

4. **Feature Engineering**: Removed StudentID before model training

## 📈 Exploratory Data Analysis

### Key Insights:
- **Balanced age distribution** across 15-18 years
- **Caucasian students** are the most represented demographic
- **Equal gender representation** in the dataset
- **Low participation** in extracurricular activities overall
- **Moderate parental support** is most common
- **Absences show the strongest correlation** (0.73) with Grade Class
- **No multicollinearity** detected among features
- **No outliers** found in numerical columns
- **Imbalanced Grade Class distribution**: Class F (failing) represents ~50% of the dataset

### Visualizations:
- Distribution plots for categorical and numerical features
- Correlation heatmaps
- Violin plots showing absences by grade class
- Grade class distribution (count plots and pie charts)

## 🤖 Model Training

### Models Implemented:
1. **Linear Regression**: Baseline model for GPA prediction
2. **Random Forest Regressor**: Ensemble method with 100 estimators

### Training Process:
- **Train-Test Split**: 70% training, 30% testing
- **Feature Scaling**: StandardScaler applied to all features
- **Random State**: 101 (for reproducibility)

### Evaluation Metrics:
- **R² Score**: Coefficient of determination
- **RMSE**: Root Mean Squared Error

## 📊 Results

The Random Forest Regressor achieved excellent performance:
- **R² Score: 0.9518** (95.18% variance explained)
- **Low RMSE**: Indicating accurate GPA predictions

This demonstrates that the model successfully captures the relationship between student characteristics and academic performance.

## 🔍 Key Findings

1. **Absences are the strongest predictor** of academic performance, showing a correlation of 0.73 with Grade Class
2. **Features are independent**, indicating no multicollinearity issues
3. **Random Forest outperforms Linear Regression** for this regression task
4. **The model achieves high accuracy** (R² = 0.9518) in predicting GPA

## 💻 Installation

1. Clone the repository:
```bash
git clone https://github.com/kathan7104/student-GPA-prediction.git
cd student-GPA-prediction
```

2. Install required packages:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy jupyter
```

3. Launch Jupyter Notebook:
```bash
jupyter notebook
```

4. Open `STD_performance.ipynb` to run the analysis

## 📖 Usage

1. Ensure the dataset `Student_performance_data _.csv` is in the project directory
2. Run the notebook cells sequentially:
   - Data loading and exploration
   - Data preprocessing
   - Exploratory data analysis
   - Model training
   - Model evaluation
3. The cleaned dataset will be saved as `cleaned_dataset.csv`

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## 👤 Author

**Kathan**
- GitHub: [@kathan7104](https://github.com/kathan7104)

## 🙏 Acknowledgments

- Dataset used for academic research purposes
- Inspired by the research paper: "Forecasting Academic Success: A Data-Driven Model for Student GPA Prediction"

---

⭐ If you find this project helpful, please consider giving it a star!

