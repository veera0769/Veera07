import pandas as pd
data = [
 {'Name': 'Alice', 'Age': 25, 'City': 'New York'},
 {'Name': 'Bob', 'Age': 30, 'City': 'Los Angeles'},
 {'Name': 'Charlie', 'Age': 35, 'City': 'Chicago'}
]
df = pd.DataFrame(data)
df.to_csv('people.csv', index=False)
df_from_csv = pd.read_csv('people.csv')
print(df_from_csv.head())
print(df_from_csv.info()
