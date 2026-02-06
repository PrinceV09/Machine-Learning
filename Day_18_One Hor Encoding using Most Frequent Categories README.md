# 🔹 One-Hot Encoding with Top-K Most Frequent Categories

---

## 📌 Problem

- High cardinality categorical features
- Too many dummy columns
- Overfitting and memory issues

---

## 💡 Solution

- Keep **Top-K most frequent categories**
- Group remaining categories as **`Other`**
- Apply **One-Hot Encoding**

---

## ⚙️ Training Data Processing

### 🔸 Step 1: Identify Top-K Categories
```python
top_categories = X_train[col].value_counts().nlargest(top_k).index
```

### 🔸 Step 2: Replace Rare Categories with `Other`
```python
X_train[col] = X_train[col].where(
    X_train[col].isin(top_categories),
    'Other'
)
```

### 🔸 Step 3: Apply One-Hot Encoding
```python
import pandas as pd

X_train = pd.get_dummies(
    X_train,
    columns=[col],
    drop_first=True
)
```

---

## 🧪 Test Data Processing

### 📍 Task
Apply the **same Top-K categories learned from training data**  
⚠️ **Do NOT recompute categories from test data**

### 🔸 Step 1: Replace Rare Categories
```python
X_test[col] = X_test[col].where(
    X_test[col].isin(top_categories),
    'Other'
)
```

### 🔸 Step 2: Apply One-Hot Encoding
```python
X_test = pd.get_dummies(
    X_test,
    columns=[col],
    drop_first=True
)
```

### 🔸 Step 3: Align Test Columns with Train Columns
```python
X_test = X_test.reindex(
    columns=X_train.columns,
    fill_value=0
)
```

✅ When to Use

- Logistic Regression

- Linear Models

- Tree-based models with high-cardinality features

⭐ Benefits

- Reduced dimensionality

- Prevents overfitting

- Memory efficient

- Production-safe encoding
