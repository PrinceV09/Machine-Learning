🔢 Encoding Techniques in Machine Learning

1️⃣ Label Encoding

📌 Definition

Converts categories into integer labels

No order is assumed

🧠 Intuition

Just assigns IDs to categories

✅ When to Use

Target variable y in classification

Tree-based models

When categories have no natural order

🧪 Python Code
from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()<br>
df['color_encoded'] = le.fit_transform(df['color'])

2️⃣ Ordinal Encoding
📌 Definition

Converts categories into numbers while preserving order

🧠 Intuition

Higher number = Higher level

Tells the model the relative ranking

✅ When to Use

When categories have a clear ranking

Education level

Size

🧪 Python Code
from sklearn.preprocessing import OrdinalEncoder

encoder = OrdinalEncoder(categories=[['High School', 'Bachelor', 'Master']])<br>
df['Education_encoded'] = encoder.fit_transform(df[['Education']])
