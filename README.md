# 🏥 Healthcare Patient No-Show Predictor

A machine learning project that predicts whether a patient
will miss their scheduled medical appointment using
real-world Brazilian hospital data.

## 📋 Problem Statement

Patient no-shows cost healthcare systems billions annually.
Predicting which patients are likely to miss appointments
allows hospitals to optimize scheduling and send targeted
reminders.

## 📊 Dataset

- **Source:** Kaggle — Medical Appointment No Shows
- **Size:** 110,527 appointments
- **Features:** Age, gender, scholarship, hypertension,
  diabetes, alcoholism, SMS received, waiting days
- **Target:** Show / No-Show (binary classification)
- **Class Balance:** 80% show, 20% no-show (imbalanced)

## 🔬 Results

### Before Class Balancing
| Model | Accuracy | Recall | F1 |
|-------|----------|--------|----|
| KNN | 70.48% | 5.77% | 10.04% |
| Naive Bayes | 67.87% | 17.25% | 23.44% |
| Logistic Regression | 71.50% | 0.22% | 0.44% |

### After Class Balancing (SMOTE Oversampling)
| Model | Accuracy | Recall | F1 | AUC |
|-------|----------|--------|----|-----|
| KNN | 59.28% | 45% | 38.83% | 0.5644 |
| Naive Bayes | 51.18% | 68% | 44.16% | 0.5692 |
| **Logistic Regression** | **55.72%** | **57%** | **42.38%** | **0.5835** |

### 🏆 Best Model: Naive Bayes (for no-show detection)
- Highest Recall (68%) — catches most no-shows
- Best F1 Score (44.16%) — best precision/recall balance
- Logistic Regression wins on AUC (0.5835)

## 💡 Key Insights

1. **Class imbalance is critical** — accuracy alone is
   misleading. Models achieving 71% accuracy were
   catching almost zero no-shows (Recall < 1%)

2. **waiting_days is strongest predictor** — longer wait
   between scheduling and appointment = higher no-show
   probability

3. **Balancing classes dramatically improved Recall**
   from 0.22% → 57% for Logistic Regression

4. **SMS reminders correlation is counterintuitive** —
   patients who received SMS had higher no-show rates
   because hospitals targeted high-risk patients

## 📁 Project Structure

\`\`\`
healthcare-no-show-predictor/
├── data/
│   ├── sample_data.csv
│   ├── X_train.npy
│   ├── X_test.npy
│   ├── y_train.npy
│   ├── y_test.npy
│   └── final_metrics.csv
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_preprocessing.ipynb
│   ├── 03_modeling.ipynb
│   └── 04_evaluation.ipynb
├── src/
│   ├── features.py
│   ├── model.py
│   └── evaluate.py
├── README.md
└── requirements.txt
\`\`\`

## 🚀 How to Run

\`\`\`bash
# Clone the repo
git clone https://github.com/yourusername/healthcare-no-show-predictor
cd healthcare-no-show-predictor

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook notebooks/
\`\`\`

## 🛠️ Skills Demonstrated

- Exploratory Data Analysis (EDA)
- Data cleaning and preprocessing
- Feature engineering (waiting days, age groups)
- Handling class imbalance (oversampling)
- Binary classification (KNN, Naive Bayes, Logistic Regression)
- Model evaluation (Accuracy, Precision, Recall, F1, AUC)
- Healthcare domain knowledge

## 👤 Author

Season Mudbhary
Website: mdatool.com
