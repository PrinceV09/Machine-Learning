🔹 What is Nominal Categorical Variable?
📌 Definition

- A Nominal Categorical Variable is a type of categorical variable in which:

- Categories have no natural order or ranking.

- Categories are just names or labels.

- Numerical comparison is not possible.

⚙️ In Machine Learning
- Nominal categorical variables are usually encoded using:

- One-Hot Encoding.

- Dummy Encoding.

🔸 One-Hot Encoding

- Creates separate binary columns for each category.

- Each column contains 0 or 1.

- Prevents the model from assuming any order.

🔸 Dummy Encoding

- Similar to One-Hot Encoding.

- Drops one column to avoid multicollinearity (dummy variable trap).

🔹 Column Transformer in Machine Learning.
📌 Definition

- A Column Transformer is used to apply different preprocessing techniques to different columns of a dataset in a single pipeline.

💡 Why Column Transformer is Needed?

- Same columns can be numerical → need scaling.

- Same columns can be categorical → need One-Hot Encoding.

- Same columns can be ordinal → need Ordinal Encoding.

🔧 Basic Syntax (sklearn)

from sklearn.compose import ColumnTransformer

ColumnTransformer(
    transformers=[
        ('name', transformer, columns)
    ],
    remainder='drop'
)
