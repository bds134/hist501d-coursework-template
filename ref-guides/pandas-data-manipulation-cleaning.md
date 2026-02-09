# Pandas Reference — Data Manipulation & Cleaning

A concise reference for common data-cleaning and manipulation tasks with pandas.

## 1. Setup

```python
import pandas as pd
import numpy as np
pd.set_option('display.max_columns', None)
```

## 2. Load & Inspect

- Read CSV / Excel / JSON:

```python
df = pd.read_csv('data.csv')
df = pd.read_excel('data.xlsx')
df = pd.read_json('data.json')
```

- Quick inspection:

```python
df.shape
df.info()
df.head()
df.tail()
df.describe(include='all') # Returns summary statistics for each column in the DataFrame 
df.columns.tolist()
df.dtypes
```

## 3. Select / Filter / Slice

- Column selection:

```python
s = df['col']
sub = df[['col1','col2']]
```

- Row selection by position or label:

```python
df.iloc[0:5]
df.loc[df['id'] == 123]
```

- Boolean filtering:

```python
mask = (df['age'] >= 18) & (df['country'] == 'US')
df_filtered = df.loc[mask]
```

## 4. Missing Values

- Detect:

```python
df.isnull().sum()
df.isna().mean()
```

- Replace placeholder strings like 'NaN' or empty strings:

```python
df = df.replace({'NaN': pd.NA, '': pd.NA})
df = df.mask(df == '')
```

- Fill or drop:

```python
df['col'].fillna('unknown', inplace=True)
df.dropna(subset=['important_col'], inplace=True)
df.dropna(axis=1, thresh=int(0.6*len(df)), inplace=True)  # drop columns with >40% missing
```

- Forward/backward fill:

```python
df.sort_values('date', inplace=True)
df['value'] = df['value'].ffill()
```

## 5. String Cleaning

- Trim whitespace, lowercase, replace patterns:

```python
df['name'] = df['name'].astype(str).str.strip()
df['city'] = df['city'].str.lower()
df['year'] = df['year'].str.replace(r'[^0-9]', '', regex=True)
```

- Normalize capitalization (title case but keep apostrophes correct):

```python
df['place'] = (df['place']
    .str.strip()
    .str.title()
    .str.replace(r"'([A-Z])", lambda m: "'" + m.group(1).lower(), regex=True)
)
```

## 6. Type Conversion

- Convert to numeric, coerce errors:

```python
df['birth_year'] = pd.to_numeric(df['birth_year'], errors='coerce').astype('Int64')
```

- Datetime parsing:

```python
df['date'] = pd.to_datetime(df['date'], errors='coerce', dayfirst=False)
```

## 7. Duplicates

- Find duplicates by subset of columns:

```python
dups = df[df.duplicated(subset=['first_name','last_name','birth_year'], keep=False)]
```

- Drop duplicates keeping first:

```python
df = df.drop_duplicates(subset=['first_name','last_name','birth_year'], keep='first')
```

## 8. Splitting / Parsing Names

- Split into parts (safe for missing values):

```python
parts = df['name'].astype(str).str.strip().str.split(r'\s+', n=2, expand=True)
df['first_name'] = parts[0]
df['middle_name'] = parts[1]
df['last_name'] = parts[2].combine_first(parts[1])
```

- Move particles (de, van, etc.) from middle to last (vectorized):

```python
particles = {'de','da','du','van','von'}
mask = df['middle_name'].notna() & df['middle_name'].str.strip().str.lower().isin(particles)
df.loc[mask, 'last_name'] = df.loc[mask, 'middle_name'].str.strip() + ' ' + df.loc[mask, 'last_name'].str.strip()
df.loc[mask, 'middle_name'] = pd.NA
```

## 9. Reshaping

- Wide to long (melt):

```python
long = df.melt(id_vars=['id','date'], value_vars=['val1','val2'], var_name='metric', value_name='value')
```

- Long to wide (pivot):

```python
wide = long.pivot_table(index=['id','date'], columns='metric', values='value', aggfunc='first').reset_index()
```

## 10. Grouping & Aggregation

```python
g = df.groupby(['country','year']).agg(
    count=('id','size'),
    mean_age=('age','mean'),
    first_seen=('date','min')
).reset_index()
```

## 11. Merges & Joins

```python
left = pd.merge(df_left, df_right, how='left', on='id', suffixes=('','_r'))
# indicator to debug merges
merged = pd.merge(a,b, on='key', how='left', indicator=True)
merged['_merge'].value_counts()
```

## 12. Window Functions

```python
df['rank'] = df.sort_values('score').groupby('group')['score'].rank(method='dense', ascending=False)
```

## 13. Performance Tips

- Use vectorized string methods (`.str.*`) and boolean masking instead of `apply`.
- Use categorical dtype for repeated strings: `df['cat'] = df['cat'].astype('category')`.
- For large joins, ensure keys are indexed or set as index.

## 14. Validation & Sanity Checks

- Quick checks:

```python
assert df['id'].is_unique
assert df['date'].notna().all()
```

- Sample problematic rows:

```python
df[df['birth_year'].isna() & df['birth_year_raw'].notna()]
```

## 15. Export

```python
df.to_csv('cleaned.csv', index=False)
df.to_parquet('cleaned.parquet')  # for faster IO
```
