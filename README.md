Here is a quick cheat sheet covering essential **pandas** operations for data exploration and cleaning, matching the workflow started in your notebook:

### 1. Basic Data Exploration

```python
import pandas as pd

# Load dataset
df = pd.read_csv("matches.csv")

# Quick Inspection
df.head()         # First 5 rows
df.tail(10)       # Last 10 rows
df.shape          # Returns tuple of (rows, columns)
df.columns        # List of column names
df.info()         # Data types, non-null counts, and memory usage
df.describe()     # Summary statistics for numerical columns

```

---

### 2. Data Cleaning Essentials

#### **A. Handling Missing Values**

```python
# Check missing values per column
df.isnull().sum()

# Drop rows with any missing value
df.dropna()

# Drop rows where specific columns have missing values
df.dropna(subset=['winner', 'city'], inplace=True)

# Fill missing values with a specific value or metric (e.g., mean/median)
df['city'].fillna('Unknown', inplace=True)
df['result_margin'].fillna(df['result_margin'].median(), inplace=True)

```

#### **B. Removing Duplicates**

```python
# Check duplicate rows
df.duplicated().sum()

# Drop duplicate rows
df.drop_duplicates(inplace=True)

```

#### **C. Data Type Conversion**

```python
# Convert data types (e.g., converting 'date' column to datetime)
df['date'] = pd.to_datetime(df['date'])

# Convert column type to integer or category
df['season'] = df['season'].astype('category')

```

#### **D. Filtering & Renaming**

```python
# Rename columns
df.rename(columns={'result_margin': 'margin'}, inplace=True)

# Filter rows based on conditions
win_margin_100 = df[df['margin'] > 100]

```Here is a quick cheat sheet covering essential **pandas** operations for data exploration and cleaning, matching the workflow started in your notebook:

### 1. Basic Data Exploration

```python
import pandas as pd

# Load dataset
df = pd.read_csv("matches.csv")

# Quick Inspection
df.head()         # First 5 rows
df.tail(10)       # Last 10 rows
df.shape          # Returns tuple of (rows, columns)
df.columns        # List of column names
df.info()         # Data types, non-null counts, and memory usage
df.describe()     # Summary statistics for numerical columns

```

---

### 2. Data Cleaning Essentials

#### **A. Handling Missing Values**

```python
# Check missing values per column
df.isnull().sum()

# Drop rows with any missing value
df.dropna()

# Drop rows where specific columns have missing values
df.dropna(subset=['winner', 'city'], inplace=True)

# Fill missing values with a specific value or metric (e.g., mean/median)
df['city'].fillna('Unknown', inplace=True)
df['result_margin'].fillna(df['result_margin'].median(), inplace=True)

```

#### **B. Removing Duplicates**

```python
# Check duplicate rows
df.duplicated().sum()

# Drop duplicate rows
df.drop_duplicates(inplace=True)

```

#### **C. Data Type Conversion**

```python
# Convert data types (e.g., converting 'date' column to datetime)
df['date'] = pd.to_datetime(df['date'])

# Convert column type to integer or category
df['season'] = df['season'].astype('category')

```

#### **D. Filtering & Renaming**

```python
# Rename columns
df.rename(columns={'result_margin': 'margin'}, inplace=True)

# Filter rows based on conditions
win_margin_100 = df[df['margin'] > 100]

```
