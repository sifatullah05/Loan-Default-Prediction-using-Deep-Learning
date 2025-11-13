# Loan Default Prediction using Artificial Neural Network (ANN)

## Project Overview

This project predicts **loan default (BAD/1)** for a set of applicants using an **Artificial Neural Network (ANN)**.  
The model is trained on a dataset containing borrower financial information, employment details, and credit history.  

The aim is to **identify high-risk borrowers**, enabling financial institutions to minimize losses due to defaults.

---

## Dataset

The dataset includes the following columns:

| Column | Description |
|--------|-------------|
| BAD    | Target variable: 1 = Default, 0 = Non-default |
| LOAN   | Amount of loan applied |
| MORTDUE| Outstanding mortgage balance |
| VALUE  | Value of current property |
| REASON | Reason for loan |
| JOB    | Job type |
| YOJ    | Years at current job |
| DEROG  | Number of major derogatory reports |
| DELINQ | Number of delinquent credit lines |
| CLAGE  | Age of oldest credit line |
| NINQ   | Number of recent credit inquiries |
| CLNO   | Number of credit lines |
| DEBTINC| Debt-to-income ratio |

> Some rows may contain missing values which were handled during preprocessing.

---

## Preprocessing Steps

1. **Missing Values Handling** – Rows with null or NaN values removed.  
2. **Feature Scaling** – All numerical features scaled using `StandardScaler`.  
3. **Class Imbalance Handling** – (Optional) `SMOTE` can be applied for balancing target classes.  
4. **Train-Test Split** – 80% training, 20% testing.

---

## Model Architecture

- **Input Layer** – 12 features  
- **Hidden Layers** – 4 layers with 64, 48, 32, 16 neurons  
- **Activation** – ReLU for hidden layers  
- **Batch Normalization** – Added after each hidden layer  
- **Output Layer** – 1 neuron, Sigmoid activation  
- **Regularization** – L2 regularization to reduce overfitting  

**Optimizer:** Adam  
**Loss Function:** Binary Crossentropy  
**Metrics:** Accuracy, Precision, Recall  

---

## Training Results

| Metric             | Training | Validation |
|-------------------|----------|------------|
| Accuracy           | 0.883    | 0.890      |
| Loss               | 0.307    | 0.289      |
| Precision          | 0.882    | 0.750      |
| Recall             | 0.883    | 0.758      |

- The model is **balanced**, with no significant overfitting.  
- Good generalization for detecting high-risk borrowers (BAD = 1).

---

## Evaluation

- **Confusion Matrix** – Shows true positives, true negatives, false positives, and false negatives.  
- **Classification Report** – Includes Precision, Recall, F1-Score.  
- **Optional Visualizations:**  
  - Training & Validation Accuracy / Loss curves  
  - ROC Curve  
  - Precision-Recall Curve  

---

## Libraries / Tools Used

- Python 3.11  
- TensorFlow / Keras  
- NumPy, Pandas  
- Matplotlib, Seaborn  
- `livelossplot` (for live training metrics visualization)  

---


