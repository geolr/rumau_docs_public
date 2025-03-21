# Python version

RHEL7: `scl enable rh-python38 bash`

`.bashrc` may contain `source scl_source enable rh-python38`

# Prep

`python3 -m venv osdu-cli-env` where last argument is the name of the environment

Don't forget to Activate the environment: `source osdu-cli-env/bin/activate`

Deactive with: `deactivate`

# Windows

(WinExpl `Shift+Rightclick` for PowerShell in current folder)

In PowerShell, the command for running python to create venv:
` & 'C:\Program Files\Pythonnnn\python.exe' -m venv windows_env`

venv on Windows seems to work to activate like this: `.\windows_env\Scripts\activate`

Once in the activate `venv`, then `pip install` just works

Try `C:\path\rumau_dev\welllogs_venv>C:\path\rumau_dev\welllogs_venv\Scripts\python.exe -m pip install --upgrade pip`

Try `C:\path\rumau_dev\welllogs_venv>C:\path\rumau_dev\welllogs_venv\Scripts\python.exe -m pip install tqdm`

List all installed packages `python.exe -m pip list`

Also `python -m jupyterlab` is OK and starts the server and all.

# Help

In interactive commandline: `help(datetime)` to get help for the datetime module, or in any other

# Libs

List all installed packages `python -m pip list`

Update: ?

Only pip upgrade: `python pip install --upgrade pip`

## Pandas

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

## Record linking
"record linkage and deduplication"
Record linkage Toolkit: https://recordlinkage.readthedocs.io

# General

Cheatsheet type of notes

## Strings

`r"C:\folder"` this is a raw string literal to avoid the double `\\`; literal backslash (as opposed to escape character in a normal string)

may want to learn about `formatted string literals` or f-strings

`f"sometext{variable} more text {another-variable}

## Pathlib

to get a string from a Path-object:
```
>>> from pathlib import Path
>>> str(Path(r"C:\Users\rm\realpython\file.txt"))
'C:\\Users\\rm\\realpython\\file.txt'
```

Recursive listing, content of subfolders:
```
# .rglob() for recursive listing

diskspace = 0

for f in p.rglob("*"):
    if f.is_dir():
        print(f, "total so far ", diskspace)
    else:
        #print(f)
        s = f.stat().st_size
        #print(type(s))
        diskspace += s
        print(f,s,"total so far:",diskspace)
print(diskspace)
```


## Loops

`for` loops => need a range of numbers or sequences of items

`while` loops => need a logical expression

* `continue`: jump back to the loop and see if more needs to be done

* `break`: leave the loop immediately

* `pass`: Do nothing
