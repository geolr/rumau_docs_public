# Pandas

From CSV-file: 
```
geo_gas = pd.read_csv('data/geo_gas_1.csv')
geo_gas.head()
```
Get some info:
```
geo_gas.info()
index                                                       38766
Realization                                                     0
Zone            NansenNansenNansenNansenNansenNansenNansenNans...
Region_index    A1A2SA2MA2NA3A4WA4EA5WA5EA5NA6A7A8A9A1020D20E1...
Bulk                                                  1.07304e+09
Net                                                    5.3989e+08
Pore                                                  1.04475e+08
Hcpv                                                  8.11572e+07
Giip                                                  2.26942e+10
dtype: object
```
`df.describe(include='all')` gives a nice overview. Mainly for statistics.

## Looking at data
`new_df.sample(n=20)` Shows a random collection of rows (instead of `df.head()`)

If reproducability is required: `df.sample(n=5, random_state=42)`

Uniqueness in dataframe:
`geo_gas.Zone.unique()`

`pd.concat` needs a `sort=True`

`pd.Series` to create an empty, needs as dtype-specified, default is now `object`

Select only some columns: 
`rawlist[["Survey name","File path"]].head()`
`df = rawlist[["Survey name","File path"]]`

`pd.json_normalize(j, record_path=['data','results'])` where j is dictionary of json, data and results are levels in the json hierarchy

In Pandas you want to use vectorized operations, **not iteration** see https://realpython.com/pandas-iterate-over-rows/

`df.to_csv('new.csv')` for export **to csv**

Pandas **adding** a list to dataframe:
I think the columns in df and elements in list have to be the same, not sure.

`df_files.loc[len(df_files)] = new_file`
* `len(df_files)` returns the current number of rows in the DataFrame.
* `df_files.loc[len(df_files)]` specifies the next row index.
* Assigning `new_file` to this location appends the list as a new row.

Viewing in **notebooks**: just `df` not `print(df)`
based on itables https://mwouts.github.io/itables/quick_start.html

Adding columns
`# Add a new column 'C' that is double the values in column 'A'`
`df['C'] = df['A'] * 2`

## Plotting

Numbers: `df.columnname.plot(kind = 'hist')`

`df.plot('columnA', 'columnname', kind = 'scatter')`

