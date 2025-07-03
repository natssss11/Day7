

## 🚀 Steps Followed

### 1. Data Preprocessing
- Loaded and cleaned the dataset.
- Converted the target labels: `M` → 1, `B` → 0.
- Applied **StandardScaler** for feature scaling.
- Split data into 80% training and 20% test set.

### 2. SVM Training
- Trained two SVM classifiers:
  - **Linear Kernel**
  - **RBF (Radial Basis Function) Kernel**
- Visualized decision boundaries after applying **PCA** for 2D projection.

### 3. Hyperparameter Tuning
- Used **GridSearchCV** to find optimal values for `C`, `gamma`, and `kernel`.

### 4. Cross-Validation
- Evaluated the model using 5-fold cross-validation.
- Cross-Validation Accuracy Scores: [0.60526316 0.55263158 0.63157895 0.61403509 0.62831858]
Mean CV Accuracy: 0.6063654712001242

---

## 📈 Results
Best Parameters: {'C': 10, 'gamma': 'scale', 'kernel': 'rbf'}
Best Score: 0.9758241758241759

### 🔹 Final Test Set Evaluation:

#### ✅ Linear SVM:
- **Accuracy:** 95.6%
- **Precision:** Class 0: 0.97 | Class 1: 0.93  
- **Recall:** Class 0: 0.96 | Class 1: 0.95  
- **F1-score:** Class 0: 0.96 | Class 1: 0.94  

#### ✅ RBF SVM:
- **Accuracy:** 98.2%
- **Precision:** Class 0: 0.97 | Class 1: 1.00  
- **Recall:** Class 0: 1.00 | Class 1: 0.95  
- **F1-score:** Class 0: 0.99 | Class 1: 0.98  

> 🎯 RBF kernel outperformed the linear kernel, showing its strength in handling complex, non-linear patterns.

---

## 📊 Key SVM Concepts Explained

### 🧮 C (Regularization Parameter)
Controls the **penalty for misclassified points**.
- High C = Low tolerance → Overfits
- Low C = More tolerance → Underfits

### 🌀 Gamma (γ)
Controls **how far a single training point’s influence reaches**.
- High gamma = Close neighbors only → Overfits
- Low gamma = Wider influence → Underfits

### 🔁 scale (Gamma Setting)
Automatically sets `gamma = 1 / (n_features * Var(X))`, adapting to feature distribution.

### 🔧 Kernel
Defines how data is **transformed into higher dimensions**.
- **Linear**: For linearly separable data
- **RBF**: For non-linear and complex boundaries (used here)

---

## 📊 Visualization
- PCA was applied to reduce feature dimensions to 2D.
- Decision boundaries of RBF SVM were plotted showing good class separation.


