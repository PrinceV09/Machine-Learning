**1. Standardization**<br>
Standardization is a Feature Scaling Technique where we transform data so that:<br>

- Mean = 0<br>
- Standard Deviation - 1<br>

**Formula**<br>
z = (Original value - Mean of the Feature)/Standard Deviation

**Example**<br>
from sklearn.preprocessing import StandardScaler
import pandas as pd

data = {
    'Age': [25, 30, 35],
    'Salary': [30000, 50000, 80000]
}

df = pd.DataFrame(data)

scaler = StandardScaler()
scaled_data = scaler.fit_transform(df)

scaled_df = pd.DataFrame(scaled_data, columns=df.columns)
print(scaled_df)

**Before Standardization**<br>
- Salary dominates distance based models.
- Age becomes almost irrelevant.

**After Standardization**<br>
- Both have mean 0 , stanard deviation 1.
- Model treats them fairly.

**Effect of outliers on Standardization**<br>
Outliers distort standardization by shifting the mean and inflating the standard deviation, compressing normal data points and reducing model performance; therefore standardization should be avoided or replaced by robust scaling when significant outliers are present.
