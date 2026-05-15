# Data Cleaning & Preprocessing with Python

A practical project focused on transforming raw, inconsistent data into a clean dataset ready for analysis and machine learning.

---

## Objective

Real-world data is messy. This project demonstrates how to systematically:

* Handle missing values
* Fix inconsistent formats
* Remove duplicates and outliers
* Prepare data for downstream tasks

---

## Workflow

```text
Raw Data → Exploration → Cleaning → Feature Processing → Final Dataset
```

---

## Project Structure

```text
Cleaning-Dataset-Using-python/
│
├── 01_Basic_Exploration/
├── 02_Numeric_Cleaning/
├── 03_Categorical_Cleaning/
├── 04_DateTime_Fixes/
├── 05_Advanced_Processing/
└── 06_Final_Output/
```

---

## Datasets

### Current Datasets (via Seaborn)

| Dataset  | Source                              | Description                                                                                           |
|----------|-------------------------------------|-------------------------------------------------------------------------------------------------------|
| Titanic  | `seaborn.load_dataset('titanic')`   | Passenger survival data — used for handling missing values, categorical encoding, and outlier removal |
| Diamond  | `seaborn.load_dataset('diamonds')`  | Gemstone pricing data — used for numeric cleaning, feature scaling, and distribution analysis         |

```python
import seaborn as sns

# Load datasets
titanic = sns.load_dataset('titanic')
diamonds = sns.load_dataset('diamonds')
```

### Upcoming Datasets

Future additions will include real-world files in the following formats:

| Format      | Examples                                   |
|-------------|--------------------------------------------|
| CSV files   | Sales records, survey results, sensor data |
| Excel files | Financial reports, student grades, HR data |

These will demonstrate cleaning workflows for file-based data using `pandas.read_csv()` and `pandas.read_excel()`.

---

## Key Techniques

**Missing Values**
* Mean / Median (numeric)
* Mode (categorical)
* Forward / Backward fill (time-series)

**Data Cleaning**
* Duplicate removal
* Type correction
* Threshold-based column dropping

**Advanced Processing**
* Outlier detection (IQR, Z-score)
* Feature scaling (StandardScaler, MinMaxScaler)

---

## Example

```python
# Load Titanic dataset via Seaborn
import seaborn as sns
titanic = sns.load_dataset('titanic')

# Fill categorical missing values
titanic['embark_town'] = titanic['embark_town'].fillna(titanic['embark_town'].mode()[0])

# Drop columns with excessive missing values
titanic.dropna(thresh=len(titanic) * 0.5, axis=1, inplace=True)

# Load Diamonds dataset and scale numeric features
diamonds = sns.load_dataset('diamonds')
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
diamonds[['price', 'carat']] = scaler.fit_transform(diamonds[['price', 'carat']])
```

---

## Results

* Missing values handled across multiple dataset types
* Datasets cleaned, consistent, and well-formatted
* Ready for machine learning pipelines

---

## Setup

```bash
git clone https://github.com/Tahir-Zaman-23DS14/Cleaning-Dataset-Using-python.git
cd Cleaning-Dataset-Using-python
pip install -r requirements.txt
```

---

## Author

**Tahir Zaman**
Data Science Student