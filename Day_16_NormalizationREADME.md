**1. Normalization** <br>
<hr>
Normalization is a technique often applied as part of data preparation for Machine Learning. The goal of Normalization is to change the values of numeric columns in the dataset to use a common scale, without distorting differences in the ranges of values or losing information.

**Min-Max Scaling** <br>

$$
x' = \frac{x - x_{\min}}{x_{\max} - x_{\min}}
$$

### Intution <br>
1. Shrinks all values into the same range.<br>
2. Preserves relative distances.<br>

### When to use <br>
- Neural Network.<br>
- Image Pixel scaling.<br>
- When features bounds are known.<br>

**Mean Normalization** <br>

Centers data around 0, scaled by range.<br>
$$
x' = \frac{x - \mu}{x_{\max} - x_{\min}}
$$

### Intution <br>
1. Combines centering + scaling.
2. Mean becomes 0.

### When to use <br>
- Gradient Descent.
- When data is fairly clean.

**MaxAbs Scaling** <br>

Scales data to [-1,1] using maximum absolute value.<br>

$$
x' = \frac{x}{|x_{\max}|}
$$

### Intution <br>
1. Keeps zero exactly zero.<br>
2. Preserves sparsity.<br>

### When to use <br>
- Sparse Data.
- NLP feature matrices.
- Data with positive abd negative values.

**Robust Scaling**

Uses Median and IQR, not Mean and Standard.<br>

$$
x' = \frac{x - Q_2}{Q_3 - Q_1}
$$

### Intution <br>
1. Ignores Extreme values.<br>
2. Focuses on Central distribution.<br>
### When to use <br>
- Real world Data.
- Finance, Sensor Data.
- Datasets with extreme values.
