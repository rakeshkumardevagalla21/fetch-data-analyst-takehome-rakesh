```python
import pandas as pd
```


```python
#load csv files
products_df = pd.read_csv("PRODUCTS_TAKEHOME.csv")
transactions_df = pd.read_csv("TRANSACTION_TAKEHOME.csv")
users_df = pd.read_csv("USER_TAKEHOME.csv")
```


```python
products_preview = products_df.head()
products_preview
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>CATEGORY_1</th>
      <th>CATEGORY_2</th>
      <th>CATEGORY_3</th>
      <th>CATEGORY_4</th>
      <th>MANUFACTURER</th>
      <th>BRAND</th>
      <th>BARCODE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Health &amp; Wellness</td>
      <td>Sexual Health</td>
      <td>Conductivity Gels &amp; Lotions</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.964944e+11</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Snacks</td>
      <td>Puffed Snacks</td>
      <td>Cheese Curls &amp; Puffs</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.327801e+10</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Health &amp; Wellness</td>
      <td>Hair Care</td>
      <td>Hair Care Accessories</td>
      <td>NaN</td>
      <td>PLACEHOLDER MANUFACTURER</td>
      <td>ELECSOP</td>
      <td>4.618178e+11</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Health &amp; Wellness</td>
      <td>Oral Care</td>
      <td>Toothpaste</td>
      <td>NaN</td>
      <td>COLGATE-PALMOLIVE</td>
      <td>COLGATE</td>
      <td>3.500047e+10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Health &amp; Wellness</td>
      <td>Medicines &amp; Treatments</td>
      <td>Essential Oils</td>
      <td>NaN</td>
      <td>MAPLE HOLISTICS AND HONEYDEW PRODUCTS INTERCHA...</td>
      <td>MAPLE HOLISTICS</td>
      <td>8.068109e+11</td>
    </tr>
  </tbody>
</table>
</div>




```python
transactions_preview = transactions_df.head()
transactions_preview
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>RECEIPT_ID</th>
      <th>PURCHASE_DATE</th>
      <th>SCAN_DATE</th>
      <th>STORE_NAME</th>
      <th>USER_ID</th>
      <th>BARCODE</th>
      <th>FINAL_QUANTITY</th>
      <th>FINAL_SALE</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0000d256-4041-4a3e-adc4-5623fb6e0c99</td>
      <td>2024-08-21</td>
      <td>2024-08-21 14:19:06.539 Z</td>
      <td>WALMART</td>
      <td>63b73a7f3d310dceeabd4758</td>
      <td>1.530001e+10</td>
      <td>1.00</td>
      <td></td>
    </tr>
    <tr>
      <th>1</th>
      <td>0001455d-7a92-4a7b-a1d2-c747af1c8fd3</td>
      <td>2024-07-20</td>
      <td>2024-07-20 09:50:24.206 Z</td>
      <td>ALDI</td>
      <td>62c08877baa38d1a1f6c211a</td>
      <td>NaN</td>
      <td>zero</td>
      <td>1.49</td>
    </tr>
    <tr>
      <th>2</th>
      <td>00017e0a-7851-42fb-bfab-0baa96e23586</td>
      <td>2024-08-18</td>
      <td>2024-08-19 15:38:56.813 Z</td>
      <td>WALMART</td>
      <td>60842f207ac8b7729e472020</td>
      <td>7.874223e+10</td>
      <td>1.00</td>
      <td></td>
    </tr>
    <tr>
      <th>3</th>
      <td>000239aa-3478-453d-801e-66a82e39c8af</td>
      <td>2024-06-18</td>
      <td>2024-06-19 11:03:37.468 Z</td>
      <td>FOOD LION</td>
      <td>63fcd7cea4f8442c3386b589</td>
      <td>7.833997e+11</td>
      <td>zero</td>
      <td>3.49</td>
    </tr>
    <tr>
      <th>4</th>
      <td>00026b4c-dfe8-49dd-b026-4c2f0fd5c6a1</td>
      <td>2024-07-04</td>
      <td>2024-07-05 15:56:43.549 Z</td>
      <td>RANDALLS</td>
      <td>6193231ae9b3d75037b0f928</td>
      <td>4.790050e+10</td>
      <td>1.00</td>
      <td></td>
    </tr>
  </tbody>
</table>
</div>




```python
users_preview = users_df.head()
users_preview
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>CREATED_DATE</th>
      <th>BIRTH_DATE</th>
      <th>STATE</th>
      <th>LANGUAGE</th>
      <th>GENDER</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5ef3b4f17053ab141787697d</td>
      <td>2020-06-24 20:17:54.000 Z</td>
      <td>2000-08-11 00:00:00.000 Z</td>
      <td>CA</td>
      <td>es-419</td>
      <td>female</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5ff220d383fcfc12622b96bc</td>
      <td>2021-01-03 19:53:55.000 Z</td>
      <td>2001-09-24 04:00:00.000 Z</td>
      <td>PA</td>
      <td>en</td>
      <td>female</td>
    </tr>
    <tr>
      <th>2</th>
      <td>6477950aa55bb77a0e27ee10</td>
      <td>2023-05-31 18:42:18.000 Z</td>
      <td>1994-10-28 00:00:00.000 Z</td>
      <td>FL</td>
      <td>es-419</td>
      <td>female</td>
    </tr>
    <tr>
      <th>3</th>
      <td>658a306e99b40f103b63ccf8</td>
      <td>2023-12-26 01:46:22.000 Z</td>
      <td>NaN</td>
      <td>NC</td>
      <td>en</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>653cf5d6a225ea102b7ecdc2</td>
      <td>2023-10-28 11:51:50.000 Z</td>
      <td>1972-03-19 00:00:00.000 Z</td>
      <td>PA</td>
      <td>en</td>
      <td>female</td>
    </tr>
  </tbody>
</table>
</div>




```python
#To check basic info and null values
products_info = products_df.info()
transactions_info = transactions_df.info()
users_info = users_df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 845552 entries, 0 to 845551
    Data columns (total 7 columns):
     #   Column        Non-Null Count   Dtype  
    ---  ------        --------------   -----  
     0   CATEGORY_1    845441 non-null  object 
     1   CATEGORY_2    844128 non-null  object 
     2   CATEGORY_3    784986 non-null  object 
     3   CATEGORY_4    67459 non-null   object 
     4   MANUFACTURER  619078 non-null  object 
     5   BRAND         619080 non-null  object 
     6   BARCODE       841527 non-null  float64
    dtypes: float64(1), object(6)
    memory usage: 45.2+ MB
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 50000 entries, 0 to 49999
    Data columns (total 8 columns):
     #   Column          Non-Null Count  Dtype  
    ---  ------          --------------  -----  
     0   RECEIPT_ID      50000 non-null  object 
     1   PURCHASE_DATE   50000 non-null  object 
     2   SCAN_DATE       50000 non-null  object 
     3   STORE_NAME      50000 non-null  object 
     4   USER_ID         50000 non-null  object 
     5   BARCODE         44238 non-null  float64
     6   FINAL_QUANTITY  50000 non-null  object 
     7   FINAL_SALE      50000 non-null  object 
    dtypes: float64(1), object(7)
    memory usage: 3.1+ MB
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 100000 entries, 0 to 99999
    Data columns (total 6 columns):
     #   Column        Non-Null Count   Dtype 
    ---  ------        --------------   ----- 
     0   ID            100000 non-null  object
     1   CREATED_DATE  100000 non-null  object
     2   BIRTH_DATE    96325 non-null   object
     3   STATE         95188 non-null   object
     4   LANGUAGE      69492 non-null   object
     5   GENDER        94108 non-null   object
    dtypes: object(6)
    memory usage: 4.6+ MB



```python
products_nulls = products_df.isnull().sum()
transactions_nulls = transactions_df.isnull().sum()
users_nulls = users_df.isnull().sum()
```


```python
# Total number of missing values across each dataframe
( products_nulls, transactions_nulls, users_nulls)
```




    (CATEGORY_1         111
     CATEGORY_2        1424
     CATEGORY_3       60566
     CATEGORY_4      778093
     MANUFACTURER    226474
     BRAND           226472
     BARCODE           4025
     dtype: int64,
     RECEIPT_ID           0
     PURCHASE_DATE        0
     SCAN_DATE            0
     STORE_NAME           0
     USER_ID              0
     BARCODE           5762
     FINAL_QUANTITY       0
     FINAL_SALE           0
     dtype: int64,
     ID                  0
     CREATED_DATE        0
     BIRTH_DATE       3675
     STATE            4812
     LANGUAGE        30508
     GENDER           5892
     dtype: int64)




```python
transactions_df['FINAL_QUANTITY'].value_counts()
```




    FINAL_QUANTITY
    1.00    35698
    zero    12500
    2.00     1285
    3.00      184
    4.00      139
            ...  
    6.22        1
    1.22        1
    1.23        1
    2.57        1
    2.27        1
    Name: count, Length: 87, dtype: int64




```python
transactions_df['FINAL_QUANTITY'].isin(['zero']).sum()  # 12,500 rows
```




    12500




```python
transactions_df['FINAL_SALE'].isin([' ']).sum()  # 12,500 rows
```




    12500



# 2nd part


```python
transactions_df['FINAL_QUANTITY'].unique()
```




    array(['1.00', 'zero', '2.00', '3.00', '4.00', '4.55', '2.83', '2.34',
           '0.46', '7.00', '18.00', '12.00', '5.00', '2.17', '0.23', '8.00',
           '1.35', '0.09', '2.58', '1.47', '16.00', '0.62', '1.24', '1.40',
           '0.51', '0.53', '1.69', '6.00', '2.39', '2.60', '10.00', '0.86',
           '1.54', '1.88', '2.93', '1.28', '0.65', '2.89', '1.44', '2.75',
           '1.81', '276.00', '0.87', '2.10', '3.33', '2.54', '2.20', '1.93',
           '1.34', '1.13', '2.19', '0.83', '2.61', '0.28', '1.50', '0.97',
           '0.24', '1.18', '6.22', '1.22', '1.23', '2.57', '1.07', '2.11',
           '0.48', '9.00', '3.11', '1.08', '5.53', '1.89', '0.01', '2.18',
           '1.99', '0.04', '2.25', '1.37', '3.02', '0.35', '0.99', '1.80',
           '3.24', '0.94', '2.04', '3.69', '0.70', '2.52', '2.27'],
          dtype=object)




```python
transactions_df['FINAL_SALE'].unique()
```




    array([' ', '1.49', '3.49', ..., '11.02', '20.17', '42.38'], dtype=object)




```python
products_df[['CATEGORY_1', 'CATEGORY_2', 'CATEGORY_3', 'CATEGORY_4']].isnull().mean()
```




    CATEGORY_1    0.000131
    CATEGORY_2    0.001684
    CATEGORY_3    0.071629
    CATEGORY_4    0.920219
    dtype: float64




```python
products_df['BARCODE'].head()  # Note scientific notation
```




    0    7.964944e+11
    1    2.327801e+10
    2    4.618178e+11
    3    3.500047e+10
    4    8.068109e+11
    Name: BARCODE, dtype: float64




```python
users_df['LANGUAGE'].value_counts(dropna=False)
```




    LANGUAGE
    en        63403
    NaN       30508
    es-419     6089
    Name: count, dtype: int64




```python
import matplotlib.pyplot as plt
import seaborn as sns

# Plot missing values across all datasets
def plot_missing(df, title):
    nulls = df.isnull().mean().sort_values(ascending=False)
    plt.figure(figsize=(10, 4))
    sns.barplot(x=nulls.index, y=nulls.values)
    plt.title(f'Missing Value Percentage - {title}')
    plt.ylabel('Proportion Missing')
    plt.xticks(rotation=45)
    plt.show()

plot_missing(products_df, "Products")
plot_missing(transactions_df, "Transactions")
plot_missing(users_df, "Users")
```


    
![png](output_17_0.png)
    



    
![png](output_17_1.png)
    



    
![png](output_17_2.png)
    



```python
# Unique non-numeric values in quantity and sale fields
print("Unique FINAL_QUANTITY values:")
print(transactions_df['FINAL_QUANTITY'].unique())

print("\nUnique FINAL_SALE values:")
print(transactions_df['FINAL_SALE'].unique())
```

    Unique FINAL_QUANTITY values:
    ['1.00' 'zero' '2.00' '3.00' '4.00' '4.55' '2.83' '2.34' '0.46' '7.00'
     '18.00' '12.00' '5.00' '2.17' '0.23' '8.00' '1.35' '0.09' '2.58' '1.47'
     '16.00' '0.62' '1.24' '1.40' '0.51' '0.53' '1.69' '6.00' '2.39' '2.60'
     '10.00' '0.86' '1.54' '1.88' '2.93' '1.28' '0.65' '2.89' '1.44' '2.75'
     '1.81' '276.00' '0.87' '2.10' '3.33' '2.54' '2.20' '1.93' '1.34' '1.13'
     '2.19' '0.83' '2.61' '0.28' '1.50' '0.97' '0.24' '1.18' '6.22' '1.22'
     '1.23' '2.57' '1.07' '2.11' '0.48' '9.00' '3.11' '1.08' '5.53' '1.89'
     '0.01' '2.18' '1.99' '0.04' '2.25' '1.37' '3.02' '0.35' '0.99' '1.80'
     '3.24' '0.94' '2.04' '3.69' '0.70' '2.52' '2.27']
    
    Unique FINAL_SALE values:
    [' ' '1.49' '3.49' ... '11.02' '20.17' '42.38']



```python
# Count number of levels used per product
products_df['category_depth'] = products_df[['CATEGORY_1', 'CATEGORY_2', 'CATEGORY_3', 'CATEGORY_4']].notnull().sum(axis=1)

sns.countplot(x='category_depth', data=products_df)
plt.title("Number of Category Levels Used per Product")
plt.xlabel("Depth of Category Hierarchy")
plt.ylabel("Number of Products")
plt.show()
```


    
![png](output_19_0.png)
    



```python
# Check barcode length (after converting to string)
products_df['BARCODE_str'] = products_df['BARCODE'].dropna().astype(str)
products_df['barcode_length'] = products_df['BARCODE_str'].str.len()

sns.histplot(products_df['barcode_length'], bins=20)
plt.title("Distribution of Barcode Lengths")
plt.xlabel("Length of Barcode (as string)")
plt.ylabel("Count")
plt.show()
```


    
![png](output_20_0.png)
    



```python

```
