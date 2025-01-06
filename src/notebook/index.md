# HR Analytics: Employee Retention Analysis

### 1. Business Problem/Context
- **Company**: Salifort Motors
- **Challenge**: High employee turnover
- **Goal**: Predict employee churn and identify contributing factors
- **Business Impact**: Reduce hiring costs and improve retention

### 2. Data Cleaning & Processing

#### Initial Data Assessment
```python
# Import required libraries
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from scipy import stats

# Read and check data
df0.info()
df0.duplicated().sum()

# Rename columns for consistency
df0 = df0.rename(columns={
    'Work_accident': 'work_accident',
    'average_montly_hours': 'average_monthly_hours',
    'time_spend_company': 'tenure',
    'Department': 'department'
})

# Remove duplicates
df1 = df0.drop_duplicates(keep='first')
```

#### Outlier Analysis Summary


**Outlier Detection Methods Explained:**
1. IQR Method (Box Plot Method)
   - Like finding shirts that are unusually small or large in a clothing store
   - Creates a "normal range" using the middle 50% of data
   - Anything too far from this range is flagged as unusual

2. Z-score Method
   - Like comparing test scores to class average
   - Measures how far each value is from the average
   - Values more than 3 standard deviations away are considered unusual

| Metric | Key Findings & Business Impact |
|--------|-------------------------------|
| Satisfaction Level | • Moderate overall mood (0.63/1.0)<br>• Some very unhappy employees (as low as 0.09)<br>• Potential risk for turnover |
| Last Evaluation | • Generally positive reviews (0.72/1.0)<br>• No extremely poor performers<br>• Consistent evaluation system |
| Project Count | • Most handle 3-4 projects<br>• Some managing 7 projects<br>• Risk of burnout at higher levels |
| Monthly Hours | • Standard 40-hour weeks on average<br>• Some working up to 77.5 hours/week<br>• Work-life balance concerns |
| Tenure | • Many outliers (824)<br>• High variation in stay duration<br>• Retention challenges evident |
| Work Accidents | • 15% accident rate<br>• Safety concerns<br>• Need for better protocols |
| Left Company | • 17% turnover rate<br>• Above industry average<br>• Immediate attention needed |
| Promotions | • Very low promotion rate (2%)<br>• Career growth concerns<br>• Potential cause of turnover |

