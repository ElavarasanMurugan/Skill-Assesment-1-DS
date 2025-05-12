# Aim : 
To explore and apply fundamental Pandas and NumPy commands for basic data handling and numerical operations.

# Algorithm :
**Step 1** :  Create a DataFrame using pd.DataFrame()

**Step 2** : Manipulate DataFrame

**Step 3** : Rename Columns

**Step 4** : Concatenate DataFrames

**Step 5** : Drop Rows or Columns

**Step 6** : Filtering & Selecting Data

**Step 7** : Sorting & Aggregation

**Step 8** : Handling Missing Values

**Step 9**: Read & Write Files

# Coding and Output :
```
import pandas as pd
#specifies values for each column
df = pd.DataFrame({"a":[4,5,6],"b":[7,8,9],"c":[10,11,12]},index=[1,2,3])
df
```
![Screenshot 2025-05-12 101114](https://github.com/user-attachments/assets/9408ff5e-e1db-41c7-9adc-1229ec11a872)

```
df1 = pd.DataFrame([[4,7,10],[5,8,11],[6,9,12]],index=[1,2,3],columns=['a','b','c'])
df1
```
![Screenshot 2025-05-12 101124](https://github.com/user-attachments/assets/bd91f1ac-a075-4680-b4f4-05f1a8dba902)

```
data = [1,2,3,4]
df2 = pd.DataFrame(data)
print (df2)

data = [['Alex',10],['Bob',12]]
df2 = pd.DataFrame(data,columns=['Name','Age'])
print (df2)

```
![Screenshot 2025-05-12 101129](https://github.com/user-attachments/assets/08e5b88c-87aa-43c8-9fca-fcfcd2ad3c5c)

```
#Column addition
data = {'Name': ['Jai', 'Princi', 'Gaurav', 'Anuj'],  'Height': [5.1, 6.2, 5.1, 5.2], 'Qualification': ['Msc', 'MA', 'Msc', 'Msc']}
df = pd.DataFrame(data)
address = ['Delhi', 'Bangalore', 'Chennai', 'Patna']
df['Address'] = address
print(df)
```
![Screenshot 2025-05-12 101135](https://github.com/user-attachments/assets/c5f60713-a734-4f99-b5ea-d5dc0e39696f)

```
#Column deletion
data = {'Name':['Jai', 'Princi', 'Gaurav', 'Anuj'],  'Age':[27, 24, 22, 32], 'Address':['Delhi', 'Kanpur', 'Allahabad', 'Kannauj'],      'Qualification':['Msc', 'MA', 'MCA', 'Phd'],'Address': ['Delhi', 'Bangalore', 'Chennai', 'Patna'] }
df = pd.DataFrame(data)
# using del function
del df['Address']
df

```
![Screenshot 2025-05-12 101141](https://github.com/user-attachments/assets/7d722c9b-da07-4f0c-8c0c-9994c720c481)

```
import pandas as pd
data = {'Name':['Jai', 'Princi', 'Gaurav', 'Anuj'],  'Age':[27, 24, 22, 32],  'Address':['Delhi', 'Kanpur', 'Allahabad', 'Kannauj'],  'Qualification':['Msc', 'MA', 'MCA', 'Phd']}
df = pd.DataFrame(data)
print(df)
df.rename(columns={'Address':'place'},inplace=True)
df
```
![Screenshot 2025-05-12 101150](https://github.com/user-attachments/assets/c9702f1e-86e0-478e-9e2e-ab8f547267c9)

```
import pandas as pd
df = pd.DataFrame([[1, 2], [3, 4]], columns = ['a','b'])
df2 = pd.DataFrame([[5, 6], [7, 8]], columns = ['a','b'])
df = pd.concat([df, df2], ignore_index=True)
df
```
![Screenshot 2025-05-12 101157](https://github.com/user-attachments/assets/b6079407-5fb8-4fe6-9313-df131bef06b7)

```
data = {'Name':['Jai', 'Princi', 'Gaurav', 'Anuj'],
        'Age':[27, 24, 22, 32],
        'Address':['Delhi', 'Kanpur', 'Allahabad', 'Kannauj'],
        'Qualification':['Msc', 'MA', 'MCA', 'Phd']}
df = pd.DataFrame(data)
df
df.drop(0,axis=0,inplace=True)
df
```
![Screenshot 2025-05-12 101202](https://github.com/user-attachments/assets/ad0fae15-5efe-4397-84a0-04bc3d1dda30)

```
import pandas as pd
data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],
        'age': [25, 32, 18, 47],
        'gender': ['F', 'M', 'M', 'M'],
        'height': [1.62, 1.78, 1.65, 1.83]}
df = pd.DataFrame(data)
df = df['name']
df
```
![Screenshot 2025-05-12 101206](https://github.com/user-attachments/assets/8210c653-699a-4f05-be8a-0cd1784f3e1e)

```
# Select only columns with the names 'name' and 'age'
df.filter(items=['name', 'age'])

# Select only columns that contain the string 'eigh'
df.filter(like='eigh')

# Select only columns that match the regular expression 'e|a'
df.filter(regex='e|a', axis=1)

# Select columns that start with 'a'
filtered_df = df.filter(regex='^a', axis=1)
print(filtered_df)
# Select columns that end with 'e'
filtered_df = df.filter(regex='e$', axis=1)
print(filtered_df)
```
![Screenshot 2025-05-12 101212](https://github.com/user-attachments/assets/2d9a8879-8067-44a5-aa0c-1192cfa0e58a)

```
data = {'name': ['Alice', 'Bob', 'Charlie', 'David', 'Emily'],
        'age': [25, 30, 35, 40, 45],
        'salary': [50000, 60000, 70000, 80000, 90000]}
df = pd.DataFrame(data)
# Get the 2 rows with the largest salary
top_salaries = df.nlargest(2, columns='salary')
print(top_salaries)

```
![Screenshot 2025-05-12 101218](https://github.com/user-attachments/assets/72ba6ff3-9d18-4b00-9fae-4125736303d6)

```
data = {'name': ['Alice', 'Bob', 'Charlie', 'David', 'Emily'],
        'age': [25, 30, 35, 40, 45],
        'salary': [50000, 60000, 70000, 80000, 90000]}
df4 = pd.DataFrame(data)
row = df4.iloc[1]
print(row)
# Select the row with the index label 2
row = df4.loc[2]
print(row)

```
![Screenshot 2025-05-12 101222](https://github.com/user-attachments/assets/fe9fe744-8962-46f6-85e2-910fa21d663d)

```
import pandas as pd
# create a sample DataFrame
data = {
    'Name': ['John', 'Sarah', 'Mike', 'Emily', 'David'],
    'Age': [25, 31, 29, 35, 27],
    'Gender': ['M', 'F', 'M', 'F', 'M'],
    'Salary': [50000, 70000, 60000, 80000, 55000]
}
df = pd.DataFrame(data)
# head method example
print(df.head(3)) # prints the first 3 rows of the DataFrame
# tail method example
print(df.tail(2)) # prints the last 2 rows of the DataFrame
# info method example
df.info() # prints the concise summary of the DataFrame, including data types and non-null values
# describe method example
print(df.describe()) # prints the descriptive statistics of the DataFrame


```
![Screenshot 2025-05-12 101231](https://github.com/user-attachments/assets/dffabc47-3729-44e5-94ba-4674cfa60054)

```
import pandas as pd
# create a sample DataFrame
data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'],
        'age': [25, 30, 35, 40],
        'score': [90, 80, 85, 95]}
df = pd.DataFrame(data)
# sort DataFrame by 'age' column in descending order
df_sorted = df.sort_values(by='age', ascending=False)
print(df_sorted)

```
![Screenshot 2025-05-12 101236](https://github.com/user-attachments/assets/0dbf4f15-c70a-4573-9ef7-c818deb447ba)

```
import pandas as pd

# Create a sample DataFrame with missing values
data = {'Name': ['Alice', 'Bob', 'Charlie', 'Dave', 'Eve'],
        'Age': [25, 32, None, 41, 28],
        'Salary': [50000, None, 70000, 90000, 60000]}
df = pd.DataFrame(data)
# Remove rows with missing values only in the 'Salary' column
df_cleaned = df.dropna(subset=['Salary'])
# Remove rows with all missing values
df_cleaned_all = df.dropna(how='all')
# Remove rows with less than 2 non-missing values
df_cleaned_thresh = df.dropna(thresh=2)
# Modify the original DataFrame by removing rows with missing values in any column
df.dropna(inplace=True)
df
```
![Screenshot 2025-05-12 101240](https://github.com/user-attachments/assets/c1988f0e-f76b-4835-83ea-3c03cb598568)

```
import pandas as pd
import numpy as np
# Create a sample DataFrame with missing values
data = {'Name': ['Alice', 'Bob', 'Charlie', 'Dave', 'Eve'],
        'Age': [25, np.nan, 35, 41, np.nan],
        'Salary': [50000, np.nan, 70000, np.nan, 60000]}
df = pd.DataFrame(data)
# Fill missing values with a constant value
df_filled = df.fillna(0)
df_filled
```
![Screenshot 2025-05-12 101244](https://github.com/user-attachments/assets/fd1f9fe3-90b1-4df7-bc92-c7d3e129faed)

CSV
```
import pandas as pd
df = pd.read_csv("/content/example - Sheet1.csv")
df

```
![Screenshot 2025-05-12 102527](https://github.com/user-attachments/assets/af7399ea-61ab-4092-b967-8ef0af1fd14e)

```
import pandas as pd
df1 = pd.read_excel('/content/example.xlsx',sheet_name='Sheet1')
df1

```
![Screenshot 2025-05-12 102531](https://github.com/user-attachments/assets/bca2bcdd-8641-448e-89d6-6fa63051ab42)

```
import pandas as pd
import numpy as np
df = pd.DataFrame({'col1':[1,2,3,4],'col2':[444,555,666,444],
			'col3':['abc','def','ghi','xyz']})
df.sort_values(by='col2')
df = pd.DataFrame(np.random.randn(10,2),
		index=[1,4,6,2,3,5,9,8,0,7],columns = ['col2','col1'])
df
df1=df.sort_index(ascending=False)
df1
df2=df.sort_index()
df2

```
![Screenshot 2025-05-12 102538](https://github.com/user-attachments/assets/5896865a-8e37-43f5-9e0f-616b2123a576)

```
import pandas as pd
# Create dataframe
data = {'Company':['GOOG','GOOG','MSFT','MSFT','FB','FB'],
       'Person':['Sam','Charlie','Amy','Vanessa','Carl','Sarah'],
       'Sales':[200,120,340,124,243,350]}
df = pd.DataFrame(data)
# Only calculate the mean for the 'Sales' column
df1 = df.groupby('Company')['Sales'].mean()
df2 = df.groupby('Company')['Sales'].std()
df3 = df.groupby('Company').min() # This will still include Person, but won't error on mean
df1
```
![Screenshot 2025-05-12 102544](https://github.com/user-attachments/assets/8efa1703-d333-4901-b8d6-ae2f21faac3b)

```
import pandas as pd
df = pd.DataFrame({'col1':[1,2,3,4],'col2':[444,555,666,444],'col3':['abc','def','ghi','xyz']})
df.head()

```
![Screenshot 2025-05-12 102548](https://github.com/user-attachments/assets/cea206f4-5a6d-4950-a2dc-c2ad04dea326)

```
df. describe()
```
![Screenshot 2025-05-12 102553](https://github.com/user-attachments/assets/871b4832-041c-4856-a9dd-c9ef5e8c2840)

```
import numpy as np
import pandas as pd
df = pd.DataFrame({'A':[1,2,np.nan],
                  'B':[5,np.nan,np.nan],
                  'C':[1,2,3]})
df
df.isnull()
df.notnull()
```
![Screenshot 2025-05-12 102557](https://github.com/user-attachments/assets/e9f7969c-0592-4979-bf48-b4602d6244b8)

```
df.dropna()
df.dropna(axis=1)
```
![Screenshot 2025-05-12 102602](https://github.com/user-attachments/assets/23e2fd72-7d06-4335-a488-caedd0834ae8)

```
df = pd.DataFrame({'A':[1,np.nan,2],
                  'B':[5,np.nan,3],
                  'C':[1,2,3]})
df
df.fillna(method='bfill')

```
![Screenshot 2025-05-12 102613](https://github.com/user-attachments/assets/9a4d5bf2-7434-47d7-956d-7bbd170784dd)



```
import pandas as pd
data = {
    'name':['Alice','Bob','Charlie','Dave'],
    'gender':['F','M','M','M'],
    'age':[25,30,35,40],
    'salary':[50000,70000,60000,80000]
}
df = pd.DataFrame(data)
# Only include numeric columns for calculating the mean
grouped = df.groupby('gender').mean(numeric_only=True)['salary']
print(grouped)
```
![Screenshot 2025-05-12 103319](https://github.com/user-attachments/assets/b21ba24e-942f-45ec-b584-8ec83facb2e7)

```
grouped_count = df.groupby('gender').count()
print(grouped_count)
```
![Screenshot 2025-05-12 103323](https://github.com/user-attachments/assets/ef97f10b-fb03-4abd-ba75-6e02326252c9)

```
import pandas as pd
data = {
    'Name':['Alice','Bob','Charlie','Dave','Eve'],
    'Age':[25,30,None,35,40],
    'Salary':[50000,None,70000,60000,80000]
}
df = pd.DataFrame(data)
df
```
![Screenshot 2025-05-12 103329](https://github.com/user-attachments/assets/5c7d77e0-9821-4b0d-95bb-e4bd1e011f81)

```
df_cleaned = df.dropna(subset=['Salary'])
print(df_cleaned)
```
![Screenshot 2025-05-12 103332](https://github.com/user-attachments/assets/4312783d-45dc-4aba-bbe4-ef9e32da05a0)

```
df_cleaned_all = df.dropna(how='all')
print(df_cleaned_all)
```
![Screenshot 2025-05-12 103337](https://github.com/user-attachments/assets/ab94e447-fbdc-4120-bb58-52f193a4ec5e)

```
df_cleaned_any = df.dropna(how='any')
print(df_cleaned_any)
```
![Screenshot 2025-05-12 103341](https://github.com/user-attachments/assets/a17ea1e9-f2c3-485b-88f3-f8a8c2bec595)

```
import pandas as pd
import numpy as np
data = {
    'Name':['Alice','Bob','Charlie','Dave','Eve','Bob','Charlie'],
    'Age':[25,np.nan,35,41,np.nan,np.nan,85],
    'Salary':[50000,np.nan,70000,np.nan,60000,np.nan,80000]
}
df = pd.DataFrame(data)
~df.duplicated()
```
![Screenshot 2025-05-12 103345](https://github.com/user-attachments/assets/94d9b075-7e61-4714-bfa4-37a9b59c8a4b)

```
df_filled = df.fillna(0)
print(df_filled)
```
![Screenshot 2025-05-12 103349](https://github.com/user-attachments/assets/14b51ae3-daca-4364-8ca7-e363b15fd3f0)

```
import pandas as pd
import numpy as np
data = {
    'Name':['Alice','Bob','Charlie','Dave','Eve'],
    'Age':[25,np.nan,35,41,np.nan],
    'Salary':[50000,np.nan,70000,np.nan,60000]
}
df = pd.DataFrame(data)
df_ffilled = df.fillna(method = 'ffill')
print(df_ffilled)
```
![Screenshot 2025-05-12 103354](https://github.com/user-attachments/assets/1ee34743-3b30-4dc7-8bac-27b752ae9d39)

```
df_bfilled = df.fillna(method = 'bfill')
print(df_bfilled)
```
![Screenshot 2025-05-12 103400](https://github.com/user-attachments/assets/d903b814-bfb6-452c-81d1-4cbf46ef62a6)

```
df_mean = df.fillna(df.select_dtypes(include=np.number).mean())
print(df_mean)
```
![Screenshot 2025-05-12 103405](https://github.com/user-attachments/assets/cc16e48b-b2eb-4771-8c5b-e42505596c28)

```
~df.duplicated()
```
![Screenshot 2025-05-12 103409](https://github.com/user-attachments/assets/1592e20d-8950-4640-bef0-c7f930dd1e63)

```
data = {'name': ['Alice', 'Bob', 'Charlie', 'Dave'], 'age': [25, 32, 18, 47], 'gender': ['F', 'M', 'M', 'M'], 'height': [1.62, 1.78, 1.65, 1.83]}
df = pd.DataFrame(data)
df_filtered = df[(df['gender'] == 'M') & (df['height']>1.7)]
# print the filtered DataFrame
print(df_filtered)
```
![Screenshot 2025-05-12 103413](https://github.com/user-attachments/assets/a1c951e7-a719-45ef-90db-330dbc8f37d2)

# Result :
The experiment successfully demonstrates fundamental Pandas and NumPy operations, enabling efficient data processing and analysis.
