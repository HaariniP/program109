# program109
import pandas as pd
df = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve', 'Frank', 'George', 'Hannah'],
    'Age': [25, 32, 18, 47, 30, 22, 55, 29],
    'City': ['New York', 'Los Angeles', 'Chicago', 'New York', 'Chicago', 'Los Angeles', 'New York', 'Los Angeles'],
    'Salary': [70000, 90000, 45000, 120000, 65000, 50000, 150000, 80000]
})
print("DataFrame:\n", df)
print("\nFirst 3 rows:\n", df.head(3))
print("\nShape:", df.shape)
print("\nStatistics:\n", df.describe())
print("\nSorted by Age:\n", df.sort_values('Age'))
print("\nAge > 30:\n", df[df['Age'] > 30])
df_dept = pd.DataFrame({'Name': df['Name'],
                        'Department': ['HR', 'Engineering', 'Sales', 'Engineering','HR', 'Sales', 'Engineering', 'HR']})
df_merged = pd.merge(df, df_dept, on='Name')
print("\nMerged DataFrame:\n", df_merged)
print("\nAverage Salary by City:\n", df.groupby('City')['Salary'].mean())
print("\nEmployee Count by Department:\n", df_merged.groupby('Department')['Name'].count())
