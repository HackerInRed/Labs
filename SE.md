### SET-1
1. **Develop a model on Analysis of Variance (ANOVA) and table for the given data:**
```python
import seaborn as sns
from scipy.stats import f_oneway
tips = sns.load_dataset('tips')

total_bills = tips.groupby('day')['total_bill'].apply(list)
f, p = f_oneway(*total_bills)

print(f'F-value: {f}')
print(f'p-value: {p}')
```

### SET-2
1. **Calculating the skewness of a data set by Pandas and SciPy:**
```python
import pandas as pd 
from scipy.stats import skew 
data = sns.load_dataset('tips')

sp = data['total_bill'].skew()
ss = skew(data['total_bill'])

print(f'Skewness (Pandas): {sp}')
print(f'Skewness (SciPy): {ss}')
```

2. **Develop a Linear Regression model for the given data:**
```python
import seaborn as sns
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split

data = sns.load_dataset('tips')

X = data[['total_bill', 'size']]
y = data['tip']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

model = LinearRegression().fit(X_train, y_train)

print("Model Score:", model.score(X_test, y_test))
```

### SET-3
1. **Design a model to calculate Percentile by SciPy and Stats Models:**
```python
import numpy as np
from scipy.stats import scoreatpercentile

d = np.random.randn(100)
p_scipy = scoreatpercentile(d, 95)
p_statsmodels = np.percentile(d, 95)
p_scipy, p_statsmodels
```

2. **Develop a Linear Regression model for the given data:**
```python
import seaborn as sns
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split

data = sns.load_dataset('tips')

X = data.drop('total_bill', axis=1).select_dtypes(include='number')
y = data['total_bill']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

model = LinearRegression()
model.fit(X_train, y_train)

score = model.score(X_test, y_test)
print(f'Model Score: {score}')
```

### SET-4
1. **Develop a model to find the variance and standard deviation of univariate statistics measures by using Pandas:**
```python
import pandas as pd 
import seaborn as sns

data = sns.load_dataset('tips')
variance = data['total_bill'].var() 
std_dev = data['total_bill'].std() 

print(f'Variance: {variance:.2f}') 
print(f'Standard Deviation: {std_dev:.2f}')
```

### SET-6
1. **Develop a model to measure covariance matrix, correlation matrix, and heat map of the given data set:**
```python
import pandas as pd 
import seaborn as sns 
import matplotlib.pyplot as plt 

data = sns.load_dataset('tips')

cov_matrix = data.cov() 
print('Covariance Matrix:\n', cov_matrix) 

corr_matrix = data.corr() 
print('Correlation Matrix:\n', corr_matrix) 

sns.heatmap(corr_matrix, annot=True)
plt.show()
```

### SET-7
1. **Develop a model on Analysis of Variance (ANOVA) and table for the given data:**
```python
import seaborn as sns
from scipy.stats import f_oneway
tips = sns.load_dataset('tips')

total_bills = tips.groupby('day')['total_bill'].apply(list)
f, p = f_oneway(*total_bills)

print(f'F-value: {f}')
print(f'p-value: {p}')
```

### SET-8
1. **Calculating the skewness of a data set by Pandas and SciPy:**
```python
import pandas as pd 
from scipy.stats import skew 
data = sns.load_dataset('tips')

sp = data['total_bill'].skew()
ss = skew(data['total_bill'])

print(f'Skewness (Pandas): {sp}')
print(f'Skewness (SciPy): {ss}')
```

### SET-9
1. **Design a model to calculate Percentile by SciPy and Stats Models:**
```python
import numpy as np
from scipy.stats import scoreatpercentile

d = np.random.randn(100)
p_scipy = scoreatpercentile(d, 95)
p_statsmodels = np.percentile(d, 95)
p_scipy, p_statsmodels
```

### SET-10
1. **Develop a model to find the variance and standard deviation of univariate statistics measures by using Pandas:**
```python
import pandas as pd 
import seaborn as sns

data = sns.load_dataset('tips')
variance = data['total_bill'].var() 
std_dev = data['total_bill'].std() 

print(f'Variance: {variance:.2f}') 
print(f'Standard Deviation: {std_dev:.2f}')
```

### SET-11
1. **Demo on Bivariate and Multivariate Descriptive Statistics measures:**
```python
import pandas as pd
import seaborn as sns

data = sns.load_dataset('tips')
correlations = data.corr()
desc_stats = data.describe()

print("Bivariate Correlations:\n", correlations, "\n")
print("Multivariate Descriptive Statistics:\n", desc_stats)
```

### SET-12
1. **Develop a model to measure covariance matrix, correlation matrix, and heat map of the given data set:**
```python
import pandas as pd 
import seaborn as sns 
import matplotlib.pyplot as plt 

data = sns.load_dataset('tips')

cov_matrix = data.cov() 
print('Covariance Matrix:\n', cov_matrix) 

corr_matrix = data.corr() 
print('Correlation Matrix:\n', corr_matrix) 

sns.heatmap(corr_matrix, annot=True)
plt.show()
```
