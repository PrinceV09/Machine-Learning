### Nominal Categorical Variable<hr>

📌 Definition

- A Nominal Categorical Variable is a type of categorical variable in which:

- Categories have no natural order or ranking.

- Categories are just names or labels.

- Numerical comparison is not possible.

### ⚙️ In Machine Learning

- Nominal categorical variables are usually encoded using:

- One-Hot Encoding.

- Dummy Encoding.

### 🔸 One-Hot Encoding

- Creates separate binary columns for each category.

- Each column contains 0 or 1.

- Prevents the model from assuming any order.

### 🔸 Dummy Encoding

- Similar to One-Hot Encoding.

- Drops one column to avoid multicollinearity
(Dummy Variable Trap).<hr>

### 🔹 Column Transformer in Machine Learning

📌 Definition

- A Column Transformer is used to apply different preprocessing techniques
to different columns of a dataset in a single pipeline.

### 💡 Why Column Transformer is Needed?

In a dataset:

- Numerical columns → need Scaling.

- Categorical columns → need One-Hot Encoding.

- Ordinal columns → need Ordinal Encoding.

➡️ Column Transformer handles all feature types together.

🔧 Basic Syntax (sklearn)<br>
from sklearn.compose import ColumnTransformer<br>

ColumnTransformer(
    transformers=[
        ('name', transformer, columns)
    ],
    remainder='drop'
)
