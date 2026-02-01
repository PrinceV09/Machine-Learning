**1. Label Encoding**<br>
<hr>
- converts categories into integer labels.<br>
- No Order is assumed.<br>
**Intution**
- Just assigns ID's to categories.<br>
- Good for target variables, not always for input features.<br>
**When to use**<br>
- target variable y in classification.<br>
- Tree based models.<br>
- When categories have no natural order.<br>
**- Python Code**<br>
<hr>
from sklearn.preprocessing import LabelEncoder<br>
le = LabelEncoder()<br>
df['color_encoded'] = le.fit_transform(df['color'])<br>

**2. Ordinal Encoding**
<hr>
- Converts categories into numbers while preserving order.<br>
**Intution**<br>
- Higher number = Higher Level<br>
- Tells model relative ranking.<br>
**When to use**<br>
- When categories have clear ranking.<br>
- Education level.<br>
- Size.<br>
**- Python Code**
<hr>
from sklearn.preprocessing import OrdinalEncoder<br>
encoder = OriginalEncoder(categories=[['High School', 'Bachelor', 'Master']])<br>
df['Education_encoded'] = encoder.fit_transform(df[['Education']])
