# Python Data Wrangling Ecosystem: Numpy & Pandas

## Import/export  dataset
CSV:
```python
pandas.read_csv('foo.csv')
my_df.to_csv('foo.csv')
```

From Excel file:
```python
pandas.read_excel('foo.xlsx', 'Sheet1', index_col=None, na_values=['NA'])
my_df.to_excel('foo.xlsx', sheet_name='Sheet1')
```

## Spliting string columns
```python
df_data = df_data.join(pandas.DataFrame(list(df_data.ExifFocalLength.str.split('/')),
                                        columns=['N', 'D']))
```

## Converting column to another type
    my_dataframe.my_column.astype(int)

## add a new column using existing ones (mutate)
    my_dataframe['new_column'] = my_dataframe.old_column * 2

## Installation and use
    pip install numpy
    pip install pandas

```python
import numpy
import pandas
```

## References
*   [http://pandas.pydata.org/]()
